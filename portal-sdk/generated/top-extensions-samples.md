<a name="portal-extension-samples"></a>
# Portal Extension Samples

 ## Overview

One of the most productive ways to learn how to develop code is by reviewing program source.  The Azure Portal team ships samples that extension developers can leverage.

All developers who install the Portal Framework SDK that is located at [http://aka.ms/portalfx/download](http://aka.ms/portalfx/download) also install the samples on their computers during the installation process. The source for the samples is located in the `Documents\PortalSDK\FrameworkPortal\Extensions\SamplesExtension` folder.

First-party extension developers, i.e. Microsoft employees, have access to the Dogfood environment, therefore they can view the samples that are located at [https://aka.ms/portalfx/viewSamples](https://aka.ms/portalfx/viewSamples).

<a name="portal-extension-samples-samples-extension"></a>
## Samples extension

The samples extension provides an individual sample for each feature available in the framework, as described in the following image.

 ![alt-text](../media/top-extensions-samples/samples.png  "Samples Extension Solution")

After installing the Portal Framework SDK, the local instance of the Portal will open with the samples extension pre-registered.  You can open the `SamplesExtension` solution file to experiment with samples in the IDE.

```bash
[My Documents]\PortalSDK\FrameworkPortal\Extensions\SamplesExtension\SamplesExtension.sln
```

The samples and the Portal can be located with **IntelliMirror** in the following location.

```bash
%LOCALAPPDATA%\PortalSDK\FrameworkPortal\Extensions\SamplesExtension\SamplesExtension.sln
```

Each sample demonstrates a single usage of the API. It is great for detailed information on any one API. You can edit the samples and then refresh the Portal to see the changes. 

For help other than documentation and samples, review the StackOverflow forum located at [https://stackoverflow.microsoft.com/questions/tagged?tagnames=ibiza](https://stackoverflow.microsoft.com/questions/tagged?tagnames=ibiza). For a list of topics and stackoverflow tags, see [portalfx-stackoverflow.md](portalfx-stackoverflow.md).

<!-- TODO: Determine whether there should be a list of samples and whether they are V1 or V2.   
The alternative is to let the list default to the contents of the SamplesExtension.sln project, and the reverse cross-reference that is created by documents like portalfx-blades-appblades.md. -->

<a name="portal-extension-samples-v1-versus-v2"></a>
## V1 versus V2

The samples are structured into two directories, **V1** and **V2**, as in the following example. 

 ![alt-text](../media/top-extensions-samples/v1-and-v2.png  "V1 and V2 Directories")

<!--TODO: Can "meant" be changed to "will"  or "intended" ? -->

<a name="portal-extension-samples-v1-versus-v2-v2"></a>
### V2

The samples in the **V2** directories use the most recent patterns. It contains the post-GA collection of new APIs that are meant to be the only set of APIs needed to develop an Ibiza extension.

The **V2** samples address the following API areas.

* New variations TemplateBlade, FrameBlade, MenuBlade 

* Blade-opening and closing `container.openBlade`, among others

* no-PDL TypeScript decorators that define all recommended Blade/Part variations

* Forms that do not use **V1** EditScope. For more information about EditScope, see [portalfx-legacy-editscopes.md](portalfx-legacy-editscopes.md).

<a name="portal-extension-samples-v1-versus-v2-v1"></a>
### V1

Our **V1** APIs use APIs that support previous UX patterns, or  are becoming obsolete or are less commonly used.  The **V1** APIs are also more difficult to use than the new API, for both the UX design and  the associated APIs.

The following **V1** concepts should not be used when **V2** APIs can be used instead.

* Blades containing Parts
* **V1** Blade-opening -- Selectable/SelectableSet APIs
* EditScope
* Fixed-width Blades
* **V1** Forms that use EditScope
* ParameterCollector/ParameterProvider
* PDL

**NOTE**: Building the **V2** space is still in process, therefore  the previously-listed **V1** concepts are not completely deprecated. For example, the source code for small, medium, and large blades is located in the `<dir>\Client\V1\Blades\BladeWidth` directory. In the meantime, use **V1** APIs in places where a **V2** replacement is not evident.

<a name="portal-extension-samples-sample-source-code"></a>
## Sample Source Code

Sample source code is included in topics that discuss the various Azure SDK API items. In the following tables, `<dir>` is the `SamplesExtension\Extension\` directory and  `<dirParent>`  is the `SamplesExtension\` directory. Links to Dogfood copies of sample experiences are included in the tables as appropriate.

Samples are primarily categorized into forms, controls, and other factors. 

* Introductions

    | API Topic             | Document                                                                                             | Sample                                                            | Experience |
    | ------------------------------ | ---------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------- | ---------- |
    | Create ARM Resource Experience | [portalfx-create-engine-sample.md](portalfx-create-engine-sample.md)                 |  | [https://aka.ms/portalfx/sampleCreateEngine](https://aka.ms/portalfx/sampleCreateEngine)  |
    | Create Custom Experience       | [portalfx-create-robot-sample.md](portalfx-create-robot-sample.md)                   |     | |
    | Forms with EditScopes          | [portalfx-legacy-editscopes.md](portalfx-legacy-editscopes.md)             | `<dir>\Client\V1\MasterDetail\MasterDetailBrowse\ViewModels\DetailViewModels.ts`.     | |`<dir>\Client\V1\MasterDetail\MasterDetailEdit\ViewModels\MasterDetailEditData.ts`  | 
    | Forms Without EditScopes       | [portalfx-forms-editscopeless.md](portalfx-forms-editscopeless.md)      |   | |
    | Getting Started with Parameters               | [portalfx-parameter-collection-getting-started.md](portalfx-parameter-collection-getting-started.md) | `<dir>\Client\V1\ParameterCollection\ ParameterCollectionArea.ts` | |
    
* All Azure API's

  | API Topic            | Document | Sample | 
  | --------------------------  | ----------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------   | 
  | Bundling and Configuration  | [portalfx-extensions-migrate-existing-to-extensioncontrollerbase.md](portalfx-extensions-migrate-existing-to-extensioncontrollerbase.md)  |       | 
   | Configuration Settings      | [portalfx-load-configuration.md](portalfx-load-configuration.md)                                                                          | `<dir>\Configuration\ArmConfiguration.cs`                                     |
  | Content Delivery Network    | [portalfx-cdn.md](portalfx-cdn.md)                                                                                                        |  `<dir>\Configuration\CustomApplicationContext.cs`                            | 
  | Localizing your extension |  [portalfx-localization.md](portalfx-localization.md) | `<dir>\Client\ClientResources.resx` | |
  | Performant Extensions       | [portalfx-extensions-bp-performance.md](portalfx-extensions-bp-performance.md)                           | `<dir>\Client\V1\Controls\Grid\ViewModels\ PageableGridViewModel.ts`          | 
  | Type metadata               | [portalfx-data-typemetadata.md](portalfx-data-typemetadata.md)                                                                            | `<dirParent>\SamplesExtension.DataModels\ SamplesExtension.DataModels.csproj` | 
  | Versioning an Extension     | [portalfx-extensions-versioning.md](portalfx-extensions-versioning.md)                                                                      | `<dir>\Content\SamplesExtension\Scripts\ MsPortalFxDocs.js`                   | 
  | Defining Extensions with TypeScript decorators  | [portalfx-no-pdl-programming.md](portalfx-no-pdl-programming.md)         | `<dir>\Client\V2\Blades\Template\ SimpleTemplateBlade.ts`        | [https://aka.ms/portalfx/sampleTypeScript](https://aka.ms/portalfx/sampleTypeScript) | 

  * Debugging and Logging

    | API Topic      | Document                                                                                         | Sample | 
    | --------------------- | ------------------------------------------------------------------------------------------------ | ------ | 
    | Logging and Debugging | [portalfx-logging-from-typescript-and-dotnet.md](portalfx-logging-from-typescript-and-dotnet.md) | `<dir>\Client\V1\Diagnostics\Logging\ ViewModels\LoggingViewModels.ts` |  
    | Logging Telemetry     | [portalfx-telemetry-logging.md](portalfx-telemetry-logging.md)                                   | `<dir>\Configuration\ApplicationConfiguration.cs` |  
    
  The following tables are categorized by the Model-View-View-Model methodology.

  * Modeling Data

    | API  Data Model Element                   | Document                                                                     | Sample | 
    | ----------------------------------- | ---------------------------------------------------------------------------- | ------ | 
    | Data View                           | [portalfx-data-overview.md](portalfx-data-overview.md)                       |  `<dir>\Client\V1\MasterDetail\MasterDetailEdit\ ViewModels\MasterViewModels.ts`  | 
    | Data Transformations                | [portalfx-data-projections.md](portalfx-data-projections.md)                 | `<dir>\Client\V1\Data\Projection\ ViewModels\MapAndMapIntoViewModels.ts`     <br> `<dir>\Client\V1\Data\Projection\ ViewModels\ProjectionBladeViewModel.ts`     <br>      `<dir>\Client/V1/Data/Projection/ViewModels/ProjectionBladeViewModel.ts`      | 
    | Extension Outputs                   | [portalfx-blades-outputs.md](portalfx-blades-outputs.md)                     |  `<dir>\Client\Bindings\OutputBindings\ OutputBindings.pdl` | 
    | Loading Data                        | [portalfx-data-loadingdata.md](portalfx-data-loadingdata.md)                 | `<dir>\Client\V1\Data\SupplyData\SupplyData.ts` | 
    | Polling and Refreshing Data         | [portalfx-data-refreshingdata.md](portalfx-data-refreshingdata.md)           | `<dir>\Client\V1\ResourceTypes\SparkPlug \SparkPlugData.ts` <br>    `<dir>\Client\V1\Hubs\RobotData.ts` <br>    `<dir>/Client/V1/Hubs/RobotData.ts` <br> `<dir>/Client/V1/Hubs/ComputerData.ts` | 
    
  * View Components
    
    | API ScreenObject           | Document | Sample | Experience |
    | -------------------------- | -------- | ------ | ---------- |
    | Browse Experience          | [portalfx-browse.md](portalfx-browse.md)                                             | `<dir>\Client\V1\Hubs\Browse\Browse.pdl` <br>  `<dir>\Client\Hubs\Browse\Services\RobotGridColumnsService.ts`  `<dir>\Client\Shared\SharedArea.ts` <br>`<dir>\Client\Hubs\Browse\Services\RobotBrowseService.ts`     | |
      | Button Parts               | [portalfx-parts.md](portalfx-parts.md)                                               | `<dir>\Client\V1\Parts\Intrinsic\ ViewModels\ButtonPartViewModel.ts` | [https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/ButtonPartIntrinsicInstructions/selectedItem/ButtonPartIntrinsicInstructions/selectedValue/ButtonPartIntrinsicInstruction](https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/ButtonPartIntrinsicInstructions/selectedItem/ButtonPartIntrinsicInstructions/selectedValue/ButtonPartIntrinsicInstruction) | 
    | Display data across blades | [portalfx-data-masterdetailsbrowse.md](portalfx-data-masterdetailsbrowse.md)         | `<dir>\Client\V1\MasterDetail\MasterDetailBrowse\ViewModels\DetailViewModels.ts`  <br>      `<dir>\Client\V1\MasterDetail\MasterDetailBrowse\ViewModels\MasterViewModels.ts`  <br>      `<dir>\Client\V1\MasterDetail\MasterDetailArea.ts`  <br>      `<dir>Client\V1\Data\MasterDetailBrowse\MasterDetailBrowseData.ts` | |
    | Essentials panel           | [portalfx-essentials.md](portalfx-essentials.md)                                     | `<dir>\Client\V1\ResourceTypes\Engine\EngineData.ts` <br>      `<dir>\Client\V1\ResourceTypes\Engine\ViewModels\EngineResourceSummaryViewModel.ts` | | 
    | Extension User Interface   | [portalfx-blades-ui.md](portalfx-blades-ui.md)                                       | `<dir>\Client\Blades\Template\ViewModels\ TemplateBladeViewModels.ts`  <br>      `<dir>\Client\ContentState\ViewModels\ContentStateViewModels.ts`      | |
    | Fx Controls in EditScope forms | [portalfx-editscopeless-procedure.md](portalfx-editscopeless-procedure.md)  [portalfx-extension-pricing-tier.md](portalfx-extension-pricing-tier.md) | `<dir>\Client\V1\Create\EngineV3\ ViewModels\CreateEngineBladeViewModel.ts` <br>      `<dir>\Client/V1/Hubs/PricingV3/ViewModels/Robot/RobotSpecPickerV3BladeViewModel.ts` <br>    `<dir>\Client/V1/Hubs/PricingV3/ViewModels/Robot/RobotSpecPickerV3Extender.ts`      | [https://aka.ms/portalfx/samplecreateengine](https://aka.ms/portalfx/samplecreateengine) | 
    | Hubs Extension             | [portalfx-hubsextension-pde.md](portalfx-hubsextension-pde.md)                       | `<dir>\Client\Hubs\PricingV3` <br>     `<dir>\Client/Hubs/ScopedBrowse/ViewModels/ScopedBrowseLauncherPartViewModel.ts`      | [https://aka.ms/portalfx/sampleHub](https://aka.ms/portalfx/sampleHub) |
    | Icon                       | [portalfx-icons.md](portalfx-icons.md)                                               | `<dir>\Client\V1\UI\ViewModels\Blades\ IconBladeViewModels.ts` | | 
    | Intrinsic Tile             | [portalfx-parts-intrinsic.md](portalfx-parts-intrinsic.md)                           | `<dir>\Client\V1\Parts\Intrinsic\ ViewModels\IntrinsicBladeViewModel.ts` | [https://aka.ms/portalfx/samples/#blade/SamplesExtension/IntrinsicPartsIndexBlade](https://aka.ms/portalfx/samples/#blade/SamplesExtension/IntrinsicPartsIndexBlade) | 
    | Pinning Parts              | [portalfx-parts-pinning.md](portalfx-parts-pinning.md)                               | `<dir>\Client\V1\Hubs\Browse\Browse.pdl` | | 
    | Portal Parts               | [portalfx-parts.md](portalfx-parts.md)  | `<dir>\Client\V1\Parts\PartsArea.ts` <br>     `<dir>\Client/V1/Parts/TileGallery/ViewModels/GeneralGalleryPart.ts`  <br>     `<dir>\Client/V1/Parts/Intrinsic/ViewModels/ButtonPartViewModel.ts` <br>     `<dir>\Client/V1/Parts/Custom/ViewModels/ExampleCustomPartViewModel.ts` <br>     `<dir>\Client/V1/Parts/PartSizes/ViewModels/PartSizesViewModels.ts`     |
    

 ### Samples Forms

  | API Topic                             | Document                                                                 | Sample                                                           | Experience |
  | ----------------------------------------------  | ------------------------------------------------------------------------ | ---------------------------------------------------------------- | ---------- |
  | Basic Forms, Form Sections, CustomHtml   | [portalfx-forms-designing.md](portalfx-forms-designing.md) | `<dir>\Client\V1\Forms\Samples\Basic\ ViewModels\Parts\FormsSampleBasicBlades.ts` <br> `<dir>\Client\V1\Forms\Samples\BasicCreate\ ViewModels\Parts\FormsSampleBasicCreatePart.ts` <br> `<dir>\Client\V1\Forms\Samples\Validations\ ViewModels\FormValidationsViewModels.ts` | [http://aka.ms/portalfx/samples#blade/SamplesExtension/SDKMenuBlade/formsallup](http://aka.ms/portalfx/samples#blade/SamplesExtension/SDKMenuBlade/formsallup) http://aka.ms/portalfx/samples#blade/SamplesExtension/CustomFormFieldsBlade  <br>  [https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/SDKMenuBlade/formsallup](https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/SDKMenuBlade/formsallup) |
  | Create Form                | [portalfx-create.md](portalfx-create.md)                                             | `<dir>\Client\V1\Create\EngineV3\ ViewModels\CreateEngineBladeViewModel.ts`      | |
  | Form Construction          | [portalfx-forms-construction.md](portalfx-forms-construction.md)                     | `<dir>\Client\V1\Forms\Samples\Basic\ ViewModels\FormsSampleBasicBlade.ts` | |
  | Form Field Validation      | [portalfx-forms-field-validation.md](portalfx-forms-field-validation.md)             | `<dir>\Client\V1\Forms\Samples\Validations\ ViewModels\FormValidationsViewModels.ts` | |
  | Testing Forms               | [portalfx-testing-filling-forms.md](portalfx-testing-filling-forms.md)                                       | `<dir>`              | 

  

 ## Samples Blades

| API Topic                             | Document                                                                 | Sample                                                           | Experience |
| ----------------------------------------------  | ------------------------------------------------------------------------ | ---------------------------------------------------------------- | ---------- |
| View Model                 | [portalfx-blade-viewmodel.md](portalfx-blade-viewmodel.md)                           | `<dir>\Client\V1\Blades\Template\ ViewModels\TemplateBladeViewModels`       |  |
| Template Blades                | [portalfx-blades-overview.md](portalfx-blades-overview.md) | `<dir>\Client\V1\Blades\Template\ ViewModels\TemplateBladeViewModels.ts` <br>     `<dir>\Client\V1\Data\ClientSideSortFilter\ViewModels\ViewModels.ts` <br>     `<dir>\Client\V1\Blades\Template\ViewModels\TemplateBladeViewModels.ts`  | |
| TemplateBlade Advanced Options | [portalfx-blades-advanced.md](portalfx-blades-advanced.md)   | `<dir>/Client/V1/Blades/Template/ViewModels/TemplateBladeViewModels.ts` <br> `<dir>/Client/V1/Blades/ContentState/ViewModels/ContentStateViewModels.ts` <br>      `<dir>/Client/V1/Blades/DynamicNotice/ViewModels/DynamicNoticeViewModels.ts` <br> `<dir>Client/V1/Blades/Unauthorized/ViewModels/UnauthorizedBladeViewModel.ts`  | 
| Blade Properties               | [portalfx-blades-properties.md](portalfx-blades-properties.md)                           | `<dir>\Client\V1\Blades\Properties\ ViewModels\BladePropertyViewModels.ts`  <br> `<dir>\Client\V1\Hubs\Browse\ViewModels\RobotBladeViewModel.ts`     | | 
| AppBlades                  | [portalfx-blades-appblades.md](portalfx-blades-appblades.md)                         | `<dir>\Client\V1\Blades\AppBlade\ ViewModels\AppBladeViewModel.ts`   |  |
| Menu Blade                     | [portalfx-blades-menublade.md](portalfx-blades-menublade.md)                             | `<dir>\Client\V1\Blades\MenuBlade\ ViewModels\SampleMenuBlade.ts`| [https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/GroupedGridInstructions](https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/GroupedGridInstructions) <br> [https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/SampleMenuBlade/bladeWithSummary](https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/SampleMenuBlade/bladeWithSummary) | 
| Pricing Tier Blade             | [portalfx-extension-pricing-tier.md](portalfx-extension-pricing-tier.md)                 | `<dir>\Client\V1\Create\EngineV3\ ViewModels\CreateEngineBladeViewModel.ts` | |
| Testing Parts and Blades    | [portalfx-testing-parts-and-blades.md](portalfx-testing-parts-and-blades.md)   |   `<dir>\Client\Blades\BladeKind\ViewModels\BladeKindsViewModels.ts` <br>  `<dir>\Client\Blades\BladeKind\ViewModels\InfoListPartViewModel.ts`  <br> `<dir>\Client\Blades\BladeKind\ViewModels\PropertiesPartViewModel.ts`  <br> `<dir>\Client\Blades\BladeKind\ViewModels\NoticePartViewModel.ts`  <br> `<dir>\Client\Blades\BladeKind\ViewModels\SettingListPartViewModel.ts`     |

<a name="portal-extension-samples-samples-index-blades"></a>
## Samples Index Blades

The following table contains blades  that display lists of controls.  These objects are not inherently controls.

| Gallery | Document | Sample | Experience |
| ------- | -------- | ------ | ---------- |
| ControlIndexBlade |  | `<dir>\Client\V1\Controls\ControlIndexBlade\ViewModels\ControlIndexViewModel.ts` |  |
| UnsupportedIndexBlade |  | `<dir>\Client\V1\Controls\UnsupportedIndexBlade\ViewModels\UnsupportedIndexViewModel.ts` |   |

 ### Samples Commands

| API Topic                             | Document                                                                 | Sample                                                           | Experience |
| ----------------------------------------------  | ------------------------------------------------------------------------ | ---------------------------------------------------------------- | ---------- |
| Opening an Extension      | [portalfx-blades-opening.md](portalfx-blades-opening.md)                                 | `<dir>\Client\V1\Commands\OpenBladeCommand\ ViewModels\OpenBladeCommandViewModels.ts` <br>     `<dir>\Client\V1\Bindings\InputBindingsDifferentBlades\ViewModels\InputBindingsDifferentBladesViewModels.ts` <br>     `<dir>\Client\Navigation\DynamicBlades\ViewModels\DynamicBladesViewModels.ts` <br> `<dir>\Client\ParameterCollection\CollectorAsHotSpot\ViewModels\CompositePartHotSpotViewModel.ts` <br>   `<dir\Client\V1\Bindings\DynamicSelectableRegistration\ViewModels\DynamicHotspots.ts` |  [http://aka.ms/portalfx/samples#blade/SamplesExtension/SDKMenuBlade/openbladeapi](http://aka.ms/portalfx/samples#blade/SamplesExtension/SDKMenuBlade/openbladeapi)  |
| Commands  | [portalfx-commands.md](portalfx-commands.md)  |   `<dir>\Client\V1\Commands\SimpleBladeCommand\ViewModels\SimpleBladeCommandViewModels.ts` <br>   `<dir>\Client\V1\Commands\Dialogs\ViewModels\CommandDialogsViewModels.ts` <br> `<dir>\Client\V1\Commands\UrlCommand\ViewModels\UrlCommandViewModels.ts` <br>    `<dir>\Client\V1\Commands\OpenBladeCommand\ViewModels\OpenBladeCommandViewModels.ts`  |      |
| Closing an Extension           | [portalfx-blades-closing.md](portalfx-blades-closing.md)                                 | `<dir>\Client\V1\Commands\OpenBladeCommand\ ViewModels\OpenBladeCommandViewModels.ts` |  [http://aka.ms/portalfx/samples#blade/SamplesExtension/SDKMenuBlade/openbladeapi](http://aka.ms/portalfx/samples#blade/SamplesExtension/SDKMenuBlade/openbladeapi) |
| Testing Commands            | [portalfx-testing-using-commands.md](portalfx-testing-using-commands.md)            |                          |
    

 
<a name="portal-extension-samples-samples-controls"></a>
## Samples Controls

Most controls are available in the playground located at  [https://aka.ms/portalfx/playground](https://aka.ms/portalfx/playground), which also generates custom code. The following tables include the location of code samples that are shipped with the SDK for developers who are not generating custom code.

The experience for the control may include a link to the Dogfood environment in addition to or instead of a link to the playground.

The documents that describe a control, if any, include information other than the three development steps. For example, a developer may need assistance in migrating from a previous edition of a control.
 
**NOTE**: In the following tables, `<dir>` is the `SamplesExtension\Extension\` directory, and  `<dirParent>`  is the `SamplesExtension\` directory, based on where the samples were installed when the developer set up the SDK. If there is a working copy of the sample in the Dogfood environment, it can be experienced by using the link in the table. 

<a name="portal-extension-samples-controls-that-are-used-by-other-controls"></a>
## Controls that are used by other controls

<!-- TODO:  Determine whether the controls that are used by other controls need to have their own document, or can just be explained in a control that uses them. Also determine whether there are more controls than just the label that belong in the list. -->

| Control        | Sample | Experience |
| -------------- | --------- | -------------- |
| CopyableLabel | `<dir>\Client\V2\Controls\ CopyableLabel\CopyableLabelBlade.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/CopyableLabelBlade |

<a name="portal-extension-samples-basic-screen-controls"></a>
## Basic Screen Controls

<!-- TODO:  Determine whether the separate documents still contain data that should be separated from the main controls-procedure document.   If so, determine whether it is appropriate for them to be combined into the following separate table.-->

Controls that do not have a link to a unique experience can be located in the playground at  [https://aka.ms/portalfx/playground](https://aka.ms/portalfx/playground) or in the selection list at [https://df.onecloud.azure-test.net/#blade/SamplesExtension/SDKMenuBlade/controls](https://df.onecloud.azure-test.net/#blade/SamplesExtension/SDKMenuBlade/controls).

| Control |  Document | Sample | Experience |
| ------- | -------- | ------ | ---------- |
| Button and SimpleButton | |  `<dir>\Client\V2\Controls\SimpleButton\ SimpleButtonBlade.ts` |  http://aka.ms/portalfx/samples#blade/SamplesExtension/SimpleButtonBlade |
| File Download Button |  | `<dir>\Client\V1\Controls\FileDownloadButton\ViewModels\ FileDownloadButtonViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/FileDownloadButtonInstructions/selectedItem/FileDownloadButtonInstructions/selectedValue/FileDownloadButtonInstructions |  
| File Upload (async) |  | `<dir>\Client\V1\Controls\AsyncFileUpload\ViewModels\ AsyncFileUploadViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/AsyncFileUploadInstructions/selectedItem/AsyncFileUploadInstructions/selectedValue/AsyncFileUploadInstructions |
| OAuth Button  | | `<dir>\Client\V2\Controls\ OAuthButton\OAuthButtonBlade.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/OAuthButtonBlade | 
| Settings | | `<dir>\Client\V1\Controls\Settings\ViewModels\ SettingsViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/SettingsInstructions/selectedItem/SettingsInstructions/selectedValue/SettingsInstructions | 
| Single Setting |   | `<dir>\Client\V1\Controls\SingleSetting\ViewModels\ SingleSettingViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/SingleSettingInstructions/selectedItem/SingleSettingInstructions/selectedValue/SingleSettingInstructions | 
| Splitter | | `<dir>\Client\V2\Controls\ Splitter\SplitterBlade.ts` |  http://aka.ms/portalfx/samples#blade/SamplesExtension/SplitterBlade | 
| TextBlock  |  | `<dir>\Client\V1\Controls\TextBlock\ViewModels\ TextBlockViewModels.ts` | https://df.onecloud.azure-test.net/?samplesExtension=true#blade/SamplesExtension/TextBlockInstructions/selectedItem/TextBlockInstructions/selectedValue/TextBlockInstructions | 
| Toolbar   | [portalfx-controls-toolbar.md](portalfx-controls-toolbar.md) <br> [portalfx-blades-procedure.md](portalfx-blades-procedure.md)  |  `<dir>\Client\V1\Controls\Toolbar\ViewModels\ ToolbarViewModels.ts` <br> `<dir>\Client\V1\Blades\Toolbar\BladeWithToolbarViewModels.ts` | [https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/SDKMenuBlade/controls](https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/SDKMenuBlade/controls) |

<a name="portal-extension-samples-advanced-screen-controls"></a>
## Advanced Screen Controls

| Control | Document | Sample | Experience |
| ------- | -------- | ------ | ---------- |
| Accordion |  | `<dir>\Client\V2\Controls\Accordion\AccordionBlade.ts` |  |
| Essentials Control | [portalfx-controls-essentials.md](portalfx-controls-essentials.md)    | `<dir>\Client\V2\Controls\Essentials\ EssentialsDefaultBlade.ts` <br>  `<dir>\Client\V2\Controls\Essentials\ EssentialsCustomLayoutBlade.ts` <br>   `<dir>\Client\V2\Controls\Essentials\EssentialsNonResourceBlade.ts` <br> `<dir>\Client\V2\Controls\Essentials\EssentialsResponsiveBlade.ts` |  [https://df.onecloud.azure-test.net/#blade/SamplesExtension/EssentialsIndexBlade/Default/selectedItem/EssentialsIndexBlade/selectedValue/EssentialsIndexBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/EssentialsIndexBlade/Default/selectedItem/EssentialsIndexBlade/selectedValue/EssentialsIndexBlade) |
| Graph | [portalfx-controls-graph-nuget.md](portalfx-controls-graph-nuget.md) | `<dir>\Client\V1\Controls\Graph\ViewModels\ GraphCustomNodesViewModels.ts` <br> `<dir>\Client\V1\Controls\Graph\ViewModels\ GraphIndexViewModels.ts` <br> `<dir>\Client\V1\Controls\Graph\ViewModels\ GraphViewModels.ts` |  |
| LogStream |  | `<dir>\Client\V1\Controls\LogStream\ViewModels\LogStreamViewModel.ts` |  |
| Metrics |  | `<dir>\Client\V1\Controls\Metrics\ViewModels\MetricsViewModels.ts` |  |
| Pill |  | `<dir>\Client\V2\Controls\Pill\ PillBlade.ts` |  |
| Preview |  | `<dir>\Client\V1\Controls\Preview\Menu\ViewModels\MenuViewModels.ts` |  |
| SearchBox |  | `<dir>\Client\V2\Controls\SearchBox\SearchBoxBlade.ts` | [https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/SearchBoxPlayground](https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/SearchBoxPlayground) |
| Storage |  | `<dir>\Client\V2\Controls\Storage\ FileShareDropDownBlade.ts` |  |
| Video |  | `<dir>\Client\V2\Controls\Video\VideoBlade.ts` | [https://df.onecloud.azure-test.net/#blade/SamplesExtension/SDKMenuBlade/styleguidevideotitle](https://df.onecloud.azure-test.net/#blade/SamplesExtension/SDKMenuBlade/styleguidevideotitle) |

<a name="portal-extension-samples-date-and-time"></a>
## Date and Time

| Date/time Object | Document | Sample | Experience |
| ---------------- | -------- | ------ | ---------- |
|  DatePicker  |  | `<dir>\Client\V2\Controls\ DatePicker\DatePickerBlade.ts` |  [https://df.onecloud.azure-test.net/#blade/SamplesExtension/DatePickerBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/DatePickerBlade) |
| DateTimePicker   |  [portalfx-controls-datetimepicker.md](portalfx-controls-datetimepicker.md)  |  `<dir>\Client\V2\Controls\ DateTimePicker\DateTimePickerBlade.ts`   | [https://df.onecloud.azure-test.net/#blade/SamplesExtension/DateTimePickerBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/DateTimePickerBlade)   |
| DateTimeRangePicker  | [portalfx-controls-datetimerangepicker.md](portalfx-controls-datetimerangepicker.md)  |   `<dir>\Client\V2\Controls\ DateTimeRangePicker\DateTimeRangePickerBlade.ts` | [https://df.onecloud.azure-test.net/#blade/SamplesExtension/DateTimeRangePickerBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/DateTimeRangePickerBlade) |
| Date Polyfills |  | `<dir>\Client\V1\Controls\DatePolyFills\ViewModels\ DatePolyFillsViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/DatePolyFillsInstructions/selectedItem/DatePolyFillsInstructions/selectedValue/DatePolyFillsInstructions |
| DayPicker  |  | `<dir>\Client\V2\Controls\ DayPicker\DayPickerBlade.ts`   |  [https://df.onecloud.azure-test.net/#blade/SamplesExtension/DayPickerBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/DayPickerBlade) |
| DurationPicker |  | `<dir>\Client\V1\Controls\DurationPicker\ViewModels\ DurationPickerViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/DurationPickerInstructions/selectedItem/DurationPickerInstructions/selectedValue/DurationPickerInstructions |
| TimePicker |  | `<dir>\Client\V1\Controls\TimePicker\ViewModels\ TimePickerViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/TimePickerInstructions/selectedItem/TimePickerInstructions/selectedValue/TimePickerInstructions |


<a name="portal-extension-samples-drop-down-controls"></a>
## Drop down controls

<!-- TODO: Determine whether it is more appropriate to have all the migration instructions located in one document, instead of one for each control. -->
| Drop Down | Document | Sample | Experience |
| --------- | -------- | ------ | ---------- |
| DropDown | [portalfx-controls-dropdown.md](portalfx-controls-dropdown.md) | `<dir>\Client\V2\Controls\ DropDown\DropDownBlade.ts` | [https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/DropDownPlayground](https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/DropDownPlayground) |
| Console   | [portalfx-controls-console.md](portalfx-controls-console.md) | `<dir>\Client\V2\Controls\ Console\ConsoleBlade.ts` <br>  `<dir>\Client\V1\Controls\Console2\ ViewModels\Console2ViewModels.ts` |  |

<a name="portal-extension-samples-editors"></a>
## Editors

| Editor      | Document | Sample | Experience |
| ----------- | -------- | ------ | ---------- |
| Code Editor | [portalfx-controls-editor.md](portalfx-controls-editor.md)    | `<dir>\Client\V1\Controls\Editor\ ViewModels\EditorViewModels.ts` <br> `<dir>\Client\V1\Controls\Editor\ ViewModels\CustomLanguageEditorViewModels.ts`      | |
| Markdown Editor  |  | `<dir>\Client\V1\Controls\Markdown\ViewModels\ MarkdownViewModels.ts`  | [https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/MarkdownPlayground](https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/MarkdownPlayground) <br>      [http://aka.ms/portalfx/samples#blade/SamplesExtension/MarkdownInstructions/selectedItem/MarkdownInstructions/selectedValue/MarkdownInstructions](http://aka.ms/portalfx/samples#blade/SamplesExtension/MarkdownInstructions/selectedItem/MarkdownInstructions/selectedValue/MarkdownInstructions)  |
| JSONEditor |  | `<dir>\Client\V1\Controls\JSONEditor\ViewModels\JSONEditorViewModels.ts` |  |

<a name="portal-extension-samples-forms-controls"></a>
## Forms controls

<!-- TODO: Determine whether there is any significant difference between a basic screen control and a forms control. -->

| Forms | Document | Sample | Experience |
| --------- | -------- | ------ | ---------- |
| CheckBox  |   |   |  [https://df.onecloud.azure-test.net/#blade/SamplesExtension/CheckBoxBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/CheckBoxBlade) |
| TriStateCheckBox |   |   |  [https://df.onecloud.azure-test.net/#blade/SamplesExtension/TriStateCheckBoxBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/TriStateCheckBoxBlade) |
| TextBox  |  [portalfx-controls-textbox.md](portalfx-controls-textbox.md)   | `<dir>\Client\V2\Controls\TextBox\TextBoxBlade.ts`  |   [https://df.onecloud.azure-test.net/#blade/SamplesExtension/TextBoxBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/TextBoxBlade) <br>  [https://aka.ms/portalfx/sampleTextBox](https://aka.ms/portalfx/sampleTextBox) |
| MultiLineTextBox  |   |  `<dir>\Client\V2\Controls\MultiLineTextBox\MultiLineTextBoxBlade.ts` |   [https://df.onecloud.azure-test.net/#blade/SamplesExtension/MultiLineTextBoxBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/MultiLineTextBoxBlade)  |
| NumericTextBox  |   |  `<dir>\Client\V2\Controls\NumericTextBox\NumericTextBoxBlade.ts` |   [https://df.onecloud.azure-test.net/#blade/SamplesExtension/NumericTextBoxBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/NumericTextBoxBlade) |
| Option Picker  |   | `<dir>\Client\V2\Controls\OptionPicker\OptionPickerBlade.ts`   |  [https://df.onecloud.azure-test.net/#blade/SamplesExtension/OptionPickerBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/OptionPickerBlade) |
| OptionsGroup | |  | [https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/OptionsGroupPlayground](https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/OptionsGroupPlayground) |
| PasswordBox  |  | `<dir>\Client\V2\Controls\Password\PasswordBoxBlade.ts`   | 	[https://df.onecloud.azure-test.net/#blade/SamplesExtension/PasswordBoxBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/PasswordBoxBlade) |
| RadioButtons  |   |  | [https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/RadioButtonsPlayground](https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/RadioButtonsPlayground) |
| SearchBox |   |   |  [http://aka.ms/portalfx/samples#blade/SamplesExtension/SearchBoxBlade/selectedItem/SearchBoxBlade/selectedValue/SearchBoxBlade](http://aka.ms/portalfx/samples#blade/SamplesExtension/SearchBoxBlade/selectedItem/SearchBoxBlade/selectedValue/SearchBoxBlade) |
| Section |   |   |  [https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/SectionPlayground](https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/SectionPlayground) |
| Slider (includes Custom Value Slider, Range Slider, and Custom Range Slider) |  | `<dir>\Client\V2\Controls\Slider\SliderBlade.ts` | [https://df.onecloud.azure-test.net/#blade/SamplesExtension/SliderBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/SliderBlade) <br> [https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/SliderPlayground](https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/SliderPlayground)   | 
| TabControl |   |  | [https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/TabControlPlayground](https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/TabControlPlayground) |

<a name="portal-extension-samples-list-controls"></a>
## List controls

| Gallery | Document | Sample | Experience |
| ------- | -------- | ------ | ---------- |
| Grid and EditableGrid |  [portalfx-controls-grid.md](portalfx-controls-grid.md) | `<dir>\Client\V2\Controls\Grid\ItemsWithDynamicCommandsBlade.ts` <br>   `<dir>\Client\V2\Controls\EditableGrid\ EditableGrid.ts` <br> `<dir>\Client\V2\Controls\EditableGrid\ EditableGridCustomValidation.ts` <br> `<dir>\Client\V2\Controls\EditableGrid\ EditableGridDependentDropDowns.ts` <br> `<dir>\Client\V2\Controls\EditableGrid\ EditableGridDynamicCellTypes.ts` <br> `<dir>\Client\V2\Controls\EditableGrid\ EditableGridMaxEntries.ts` <br> `<dir>\Client\V2\Controls\EditableGrid\ EditableGridOperations.ts` <br> `<dir>\Client\V2\Controls\EditableGrid\ EditableGridValidation.ts` | https://df.onecloud.azure-test.net/?SamplesExtension=true#blade/SamplesExtension/BasicGridInstructions <br> http://aka.ms/portalfx/samples#blade/SamplesExtension/EditableGridInstructions |
| Grid and Grid Controls     | [portalfx-controls-grid.md](portalfx-controls-grid.md)                               | `<dir>\Client\V1\Controls\Grid\ ViewModels\ScrollableGridWithFilteringAndSorting.ts`     `<dir>/Client/V1/Controls/Grid/ViewModels/BasicGridViewModel.ts`     `<dir>Client/V1/Controls/Grid/ViewModels/FormattedGridViewModel.ts`      | [http://aka.ms/portalfx/samples#blade/SamplesExtension/GridInstructions/selectedItem/GridInstructions/selectedValue/GridInstructions](http://aka.ms/portalfx/samples#blade/SamplesExtension/GridInstructions/selectedItem/GridInstructions/selectedValue/GridInstructions) |
| ListView |  |  `<dir>\Client\V1\Controls\ListView\ViewModels\BasicListViewViewModels.ts` <br>  `<dir>\Client\V1\Controls\ListView\ViewModels\CustomListViewViewModels.ts` <br>  `<dir>\Client\V1\Controls\ListView\ViewModels\IndexViewModels.ts` <br>  `<dir>\Client\V1\Controls\ListView\ViewModels\ListViewChildBladeViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/ListViewInstructions/selectedItem/ListViewInstructions/selectedValue/ListViewInstructions |
| Tree View|  | `<dir>\Client\V1\Controls\Tree\TreeBlade.ts`  `<dir>\Client\V1\Controls\Tree\TreeItemBlade.ts`  |   [http://aka.ms/portalfx/samples#blade/SamplesExtension/TreeBlade](http://aka.ms/portalfx/samples#blade/SamplesExtension/TreeBlade)
| String List | | |http://aka.ms/portalfx/samples#blade/SamplesExtension/StringListInstructions/selectedItem/StringListInstructions/selectedValue/StringListInstructions

<a name="portal-extension-samples-helpers-and-indicators"></a>
## Helpers and Indicators

| Helpers |Sample | Experience |
| ------- |  ------ | ---------- |
| InfoBalloon |  `<dir>\Client\V1\Controls\DockedBalloon\ViewModels\DockedBalloonViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/DockedBalloonInstructions/selectedItem/DockedBalloonInstructions/selectedValue/DockedBalloonInstructions  |
| InfoBox |   `<dir>\Client\V2\Controls\Infobox\InfoboxBlade.ts` | [https://df.onecloud.azure-test.net/#blade/SamplesExtension/InfoBoxBlade](https://df.onecloud.azure-test.net/#blade/SamplesExtension/InfoBoxBlade) |
| ProgressBar |   `<dir>\Client\V1\Controls\ProgressBar\ViewModels\ProgressBarViewModels.ts` |  [https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/ProgressBarPlayground](https://ms.portal.azure.com/?Microsoft_Azure_Playground=true#blade/Microsoft_Azure_Playground/ControlsIndex/ProgressBarPlayground) <br> [http://aka.ms/portalfx/samples#blade/SamplesExtension/ProgressBarInstructions/selectedItem/ProgressBarInstructions/selectedValue/ProgressBarInstructions](http://aka.ms/portalfx/samples#blade/SamplesExtension/ProgressBarInstructions/selectedItem/ProgressBarInstructions/selectedValue/ProgressBarInstructions)  |

<a name="portal-extension-samples-data-visualization-objects"></a>
## Data Visualization Objects

| Screen Objects  | Document | Sample | Experience |
| ------------- | -------- | ------ | ---------- |
| | |  <p align="center">Aggregates</p> | |
| Controls Chart    | [portalfx-controls-chart.md](portalfx-controls-chart.md)     |  `<dir>\Client\V1\Controls\Chart\ViewModels\BarChartViewModels.ts` <br>     `<dir>\Client\V1\Controls\Chart\ViewModels\OverlayedViewChartViewModel.ts` `\Client\Controls\Chart\ViewModels\LineChartDateBasedViewModels.ts` |  |
| Plotting Metrics  (Monitor Chart and Monitor Chart V2)       | [portalfx-controls-monitor-chart.md](portalfx-controls-monitor-chart.md) | `<dir>\Client\V2\Preview\MonitorChart\ MonitorChartBlade.ts`     | [https://aka.ms/portalfx/sampleMonitorChart](https://aka.ms/portalfx/sampleMonitorChart) |
| Donut         | [portalfx-controls-donut.md](portalfx-controls-donut.md) | `<dir>\Client\V2\Controls\Donut\DonutBlade.ts`  | |
|       | | <p align="center">Gauges</p>   | |
| Quota Gauge   | | | [https://aka.ms/portalfx/playground](https://aka.ms/portalfx/playground)  |   
| Single Value Gauge | |  | [https://aka.ms/portalfx/playground](https://aka.ms/portalfx/playground)  |  
| | |<p align="center">Graphs</p>    | | |
| CustomHtml | | | http://aka.ms/portalfx/samples#blade/SamplesExtension/graphCustomNodeInstructions |
| Standard Graph  | [portalfx-controls-graph-nuget.md](portalfx-controls-graph-nuget.md)| | http://aka.ms/portalfx/samples#blade/SamplesExtension/graphInstructions |
| | | <p align="center">Maps</p>  | |
| Base Map | | | http://aka.ms/portalfx/samples#blade/SamplesExtension/BaseMapInstructions |
| Hexagon Layout Map | | |http://aka.ms/portalfx/samples#blade/SamplesExtension/HexagonMapInstructions |
| HotSpot | | | http://aka.ms/portalfx/samples#blade/SamplesExtension/HotSpotInstructions/selectedItem/HotSpotInstructions/selectedValue/HotSpotInstructions |
| Legend | | `<dir>\Client\V1\Controls\Legend\ViewModels\LegendViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/Legend/selectedItem/Legend/selectedValue/Legend  | 
| Log Stream | | | http://aka.ms/portalfx/samples#blade/SamplesExtension/LogStreamInstructions/selectedItem/LogStreamInstructions/selectedValue/LogStreamInstructions |
| Menu | | |http://aka.ms/portalfx/samples#blade/SamplesExtension/MenuInstructions/selectedItem/MenuInstructions/selectedValue/MenuInstructions |
| Spec Comparison Table | | | http://aka.ms/portalfx/samples#blade/SamplesExtension/SpecComparisonTableInstructions/selectedItem/SpecComparisonTableInstructions/selectedValue/SpecComparisonTableInstructions |


 ## Deprecated controls

The following controls have been deprecated.  They have been replaced with more performant controls, or  with best practices that reduce issues in usability testing and improve the Create success rate. However, they are included in the following list for backward compatibility.

| Control  | Document | Sample | Experience |
| -------- | -------- | ------ | ---------- |
| AzureMediaPlayer | Unsupported | Reserved for Azure media services team  |
| DataNavigator for Virtualized Data  | [portalfx-data-virtualizedgriddata.md](portalfx-data-virtualizedgriddata.md) | `<dir>\Client\V1\Controls\Grid\Templates\ PageableGridViewModel.ts` <br>      `<dir>\Client\V1\Controls\ProductData.ts`  <br>    `<dir>\Client\V1\Controls\ProductPageableData.ts`     | 
| DiffEditor  | Obsolete. Use  Code editor instead. | `<dir>\Client\V1\Controls\DiffEditor\ViewModels\DiffEditorViewModels.ts` |  http://aka.ms/portalfx/samples#blade/SamplesExtension/DiffEditorInstructions/selectedItem/DiffEditorInstructions/selectedValue/DiffEditorInstructions | 
| Drop Down  | Obsolete.  Use V2 control instead.  | `<dir>\Client\V1\Controls\ DropDown\ViewModels\DropDownViewModels.ts`  | |
| Essentials Control | Obsolete.  Use V2 control instead.  | `<dir>\Client\V1\Controls\Essentials\ViewModels\DefaultEssentialsViewModel.ts`  <br> `<dir>\Client\V1\Controls\Essentials\ViewModels\IndexViewModels.ts`  | |
| Gallery | Obsolete. | `<dir>\Client\V1\Controls\Gallery\ViewModels\GalleryViewModels.ts` |  |
| HotSpot | Obsolete. Use fx click instead. | `<dir>\Client\V1\Controls\HotSpot\ViewModels\HotSpotViewModels.ts` |  |
| IFrame |  Obsolete. | `<dir>\Client\V1\Controls\IFrame\ViewModels\IFrameViewModels.ts` |  |
| Map | Obsolete.  | `<dir>\Client\V1\Controls\Map\ViewModels\BaseMapViewModels.ts` <br> `<dir>\Client\V1\Controls\Map\ViewModels\HexagonLayoutViewModels.ts` <br> `<dir>\Client\V1\Controls\Map\ViewModels\IndexViewModels.ts`  |  |
| PairedTimeline |  Unsupported.  Reserved for partner use. <!-- TODO:  Locate one partner team that still uses this. --> | `<dir>\Client\V1\Controls\PairedTimeline\ViewModels\PairedTimelineViewModels.ts` |  |
| QueryBuilder | Obsolete.  Use pill control instead, or build a custom control for complicated queries.  | `<dir>\Client\V1\Controls\QueryBuilder\ViewModels\QueryBuilderViewModels.ts` |  http://aka.ms/portalfx/samples#blade/SamplesExtension/QueryBuilderInstructions/selectedItem/QueryBuilderInstructions/selectedValue/QueryBuilderInstructions |
| Selector | Obsolete. Use single blade experiences and fx clicks to launch blades | `<dir>\Client\V1\Controls\Selector\ViewModels\SelectorViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/SelectorInstructions/selectedItem/SelectorInstructions/selectedValue/SelectorInstructions |
| Single Setting |   | `<dir>\Client\V1\Controls\SingleSetting\ViewModels\ SingleSettingViewModels.ts` | http://aka.ms/portalfx/samples#blade/SamplesExtension/SingleSettingInstructions/selectedItem/SingleSettingInstructions/selectedValue/SingleSettingInstructions | 
| SpecComparisonTable | Obsolete.   | `<dir>\Client\V1\Controls\SpecComparisonTable\ViewModels\SpecComparisonTableViewModels.ts` |  |
| Step Gauge | Deprecated. Do not use. | |  |
| StringList |   Obsolete.  Use pill control instead, or build a custom control for complicated queries. | `<dir>\Client\V1\Controls\StringList\ViewModels\StringListViewModels.ts` |  |
| Terminal Emulator | Obsolete. Use the V2 Console instead. | |  |
| TokenComboBox |  Obsolete. Use the  V2 Dropdown box instead. | `<dir>\Client\V1\Controls\TokenComboBox\ViewModels\TokenComboBoxViewModels.ts` |  |


 ## Procedures for Portal Sample Source Code

After installing Visual Studio and the Portal Framework SDK, locate the samples in the `...\Documents\PortalSDK\FrameworkPortal\Extensions\SamplesExtension` folder.

Open the `SamplesExtension` solution file to experiment with samples in the IDE.

You can make changes to the samples as appropriate.

Click the F5 key to start debugging the sample extensions. This rebuilds the project, which will allow you to check for items like the most recent version of the SDK.

Sideload the extension. When it loads, click on the `More Services` option in the menu, as in the following example.

 ![alt-text](../media/top-extensions-samples/samples-services.png  "Portal Extensions Services")

In the filter box, search for "Azure Portal SDK". You can use `Shift + Space` to mark it as a favorite site.

Make changes to the sample that best fits the needs of the development project, then refresh the Portal to view the changes. 

 
 ## Frequently asked questions


<!-- TODO:  FAQ Format is ###Link, ***title***, Description, Solution, 3 Asterisks -->
<a name="portal-extension-samples-data-visualization-objects-samples-will-not-compile"></a>
### Samples will not compile

***How do I fix this?***

 Description:
 Right out of the box, the samples are not aware of whether V1 or V2 is being used, or whether the IDE options match the version. There may be an error message TS1219.  Errors may also occur based on the version of the SDK.

 SOLUTION:  Add a `tsconfig.json` file to the project that specifies that decorators are experimental, as in the following code.

 ```cs
 {
  "compilerOptions": {
    "noImplicitAny": false,
    "noEmitOnError": true,
    "removeComments": false,
    "sourceMap": true,
    "target": "es5",
    "experimentalDecorators": true
  },
  "exclude": [
    "node_modules"
  ]
}
 ```
 
 For more information, see [https://stackoverflow.com/questions/35460232/using-of-typescript-decorators-caused-errors](https://stackoverflow.com/questions/35460232/using-of-typescript-decorators-caused-errors).

 * * *

<a name="portal-extension-samples-data-visualization-objects-cannot-launch-iis"></a>
### Cannot launch IIS

*** Unable to launch the Microsoft Visual Studio IIS Express Web server***

Description:
Failed to register URL "https://localhost:44306/" for site "SamplesExtension" application "/". Error description: Cannot create a file when that file already exists. (0x800700b7)

SOLUTION:  Terminate IIS express processes in Task Manager and click F5 again.

* * *

 {"gitdown": "include-file", "file": "../templates/portalfx-portalfx-editscopeless-forms.md