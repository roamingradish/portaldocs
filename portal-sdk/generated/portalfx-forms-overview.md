
<a name="overview"></a>
## Overview

Form controls are a subset of controls that allow users to input information.  These controls provide a consistent API surface for managing validation, variable states, and user input.  They also provide a consistent layout structure.
  
Everything that applies to controls also applies to form controls, as specified in [top-extensions-controls.md](top-extensions.controls.md).

<a name="overview-form-control-view-model-contract"></a>
### Form control view model contract

The following properties and methods are present on all form controls.

**value**: The value property is bound to the value shown in the control. You can subscribe to it in order to respond to user input, and you can set it to update the widget's value programmatically. This property is configurable.

**disabled**: Setting this property to `true` stops the user from entering data into the control.  It will also prevent validation from running, because if validation fails, there is no way for the user to correct the value of this control.  This property also shows the user that the control is disabled by changing the styling and aria attributes. This property is configurable.

**dirty**: The dirty property is bound to the edit state of the control.  It is changed from `false` to `true` if the user changes the `value` property by interacting with the control.  Setting the `value` property programmatically will not affect the `dirty` state of the control. Additionally, when a blade is closed, and there are dirty fields present, a popup is displayed that warns the user that they might lose their input.  This alert is suppressed when the blade is closed programmatically with the blade close APIs, and data is sent back to the parent blade.  Additionally, developers can control the behavior of this alert by using the `Context.Form.ConfigureAlertOnClose` method, where context is the blade context object. This property is configurable.

  **NOTE**: The framework never resets this property from `true` back to `false`, because the framework does not track the original values of the control.  To set or reset this property programmatically, just write to it as you would any other observable.

**validations**: Validations are run whenever the control value changes, when the validations array changes, or whenever the extension calls `triggerValidation` programmatically.  If the validations fail, the control will be marked as invalid, and the validation message will be shown below the control.  In addition, if this collection contains a "Required" validation, a red asterisk will be displayed next to the label of the control that signifies to users that a value is required to proceed. This property is configurable.

  **NOTE**: The extension can programmatically trigger validation on all visible form fields by using  `context.Form.TriggerValidation`, where context is the blade context object.

**validationResults**: This property is a reflection over the current state of all validations on the control. This property is read-only and is not configurable, although an extension can subscribe to it.

**valid**: This property reflects the current validation state of the control. This property is read-only and is not configurable, although an extension can subscribe to it.

**label, sublabel, infoBalloonContent**: These properties allow the extension to display information that describes the control.  These properties will only appear in the widget if their values were set.  The label property is displayed above or to the right of the control.  The sublabel is typically shown below and to the left of the control.  The info balloon will be shown next to the label.  See the [Form Layout](#form-layout) on how to change layout.  Configuring these properties will also display information in accessible ways by using aria attributes.

**triggerValidation**: This method runs all validations on the control.  It will return a `promise` with the overall valid state of the control after validation has completed. This property is read-only and is not configurable, although an extension can subscribe to it.

<a name="form-control-input-options"></a>
## Form control input options

All configurable properties on the control, like `value`, `validations`, or `dirty`, are options that can be sent as either observables or non-observables.  Observable values are best used when one observable is already present and you do not want to set up the two-way binding. For example, you could send the same observable as the `disabled` property to multiple forms, and then disable all of the forms at once by setting that observable only once. For more information about observables, see [portalfx-blades-viewmodel.md#observable-and-non-observable-values](portalfx-blades-viewmodel.md#observable-and-non-observable-values).

**NOTE**:  For the most part, sending in non-observables is recommended because it makes extension code more readable and less verbose.

**suppressDirtyBehavior**: This is used when the form control is not being used for saving data. When this flag is set to true, the control will not mark itself as `dirty` when the value is changed.  This will prevent dirty styling, and prevent this control from triggering the alert when blades are closed.  For example, if you have a slider that controls the zoom level of a view, information like the slider position is lost when the blade is closed, but that setting is not relevant.

**NOTE**: This property is not configurable after creation of the control.

<a name="form-control-input-options-form-layout"></a>
### Form Layout

Because form controls are often grouped together, it is important to keep the layout of the controls consistent. Consequently, most form layout is controlled by using sections. For more information about sections, see  [http://aka.ms/portalfx/playground](http://aka.ms/portalfx/playground).

The section has two properties that allow for layout control. They are as follows.

**leftLabelPosition**: When this property is set to true, the labels of child form controls are placed to the left of the control, instead of above the control.  The controls themselves are aligned vertically, a few pixels to the right of the longest label.

**LeftLabelWidth**: When this property is set to true, the labels of the child form controls are placed to the left of the control, instead of above the control.  The control labels have a fixed width that is set to the number of pixels that was sent to the control. 

<a name="form-control-input-options-legacy-integration"></a>
### Legacy Integration

If you are working with blades that use legacy concepts like `editScope`, you can still use the new form controls by sending the `editScope` observable to the blade options as the `value` property. This results in the `editScope` being updated when the control is updated, and vice versa.

**NOTE**:  EditScopes are becoming obsolete.  It is recommended that extensions and forms be developed without edit scopes, as specified in [portalfx-editscopeless-procedure.md](portalfx-editscopeless-procedure.md).

<a name="form-control-input-options-form-topics"></a>
### Form Topics

There are a number of subtopics in the forms topic.  Sample source code is included in subtopics that discuss the various Azure SDK API items.

| API Topic                        | Document                                                                                     | 
| -------------------------------- | -------------------------------------------------------------------------------------------- | 
| Designing and Arranging the Form | [top-forms-designing.md](top-forms-designing.md)                                   |  
| Forms Construction               | [top-forms-construction.md](top-forms-construction.md)                             |  
| Integrating Forms with Commands  | [top-forms-integrating-with-commands.md](top-forms-integrating-with-commands.md)   | 
| Form Field Validation            | [top-forms-field-validation.md](top-forms-field-validation.md)                     | 
| Sample Extensions with Forms     | [portalfx-extensions-samples-forms.md](portalfx-extensions-samples-forms.md)                 |

For more information about how forms and parameters interact with an extension, see [portalfx-parameter-collection-overview.md](portalfx-parameter-collection-overview.md).

For more information about forms with editScopes, see [portalfx-legacy-editscopes.md](portalfx-legacy-editscopes.md).

For more information about forms without editScopes, see [portalfx-editscopeless-overview.md](portalfx-editscopeless-overview.md).