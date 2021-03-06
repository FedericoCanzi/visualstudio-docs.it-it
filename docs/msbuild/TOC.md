# [MsBuild](msbuild.md)
## [Novità di MSBuild 15.0](what-s-new-in-msbuild-15-0.md)
## [Concetti relativi a MSBuild](msbuild-concepts.md)
### [Proprietà di MSBuild](msbuild-properties.md)
#### [Procedura: Usare le variabili di ambiente in una compilazione](how-to-use-environment-variables-in-a-build.md)
#### [Procedura: Fare riferimento al nome o al percorso del file di progetto](how-to-reference-the-name-or-location-of-the-project-file.md)
#### [Procedura: Compilare gli stessi file di origine con opzioni diverse](how-to-build-the-same-source-files-with-different-options.md)
#### [Funzioni delle proprietà](property-functions.md)
### [Elementi MSBuild](msbuild-items.md)
#### [Procedura: Selezionare i file da compilare](how-to-select-the-files-to-build.md)
#### [Procedura: Escludere file dalla compilazione](how-to-exclude-files-from-the-build.md)
#### [Procedura: Visualizzare un elenco di elementi separati da virgole](how-to-display-an-item-list-separated-with-commas.md)
#### [Definizioni degli elementi](item-definitions.md)
#### [Funzioni Item](item-functions.md)
#### [Rilevamento file](file-tracking.md)
##### [EndTrackingContext](endtrackingcontext.md)
##### [ResumeTracking](resumetracking.md)
##### [SetThreadCount](setthreadcount.md)
##### [StartTrackingContext](starttrackingcontext.md)
##### [StartTrackingContextWithRoot](starttrackingcontextwithroot.md)
##### [StopTrackingAndCleanup](stoptrackingandcleanup.md)
##### [SuspendTracking](suspendtracking.md)
##### [WriteAllTLogs](writealltlogs.md)
##### [WriteContextTLogs](writecontexttlogs.md)
### [Destinazioni di MSBuild](msbuild-targets.md)
#### [Ordine di compilazione delle destinazioni](target-build-order.md)
#### [Compilazioni incrementali](incremental-builds.md)
#### [Procedura: Specificare quale destinazione compilare per prima](how-to-specify-which-target-to-build-first.md)
#### [Procedura: Usare la stessa destinazione in più file di progetto](how-to-use-the-same-target-in-multiple-project-files.md)
#### [Procedura: Compilare destinazioni specifiche all'interno di soluzioni tramite MSBuild.exe](how-to-build-specific-targets-in-solutions-by-using-msbuild-exe.md)
#### [Procedura: Eseguire la compilazione incrementale](how-to-build-incrementally.md)
#### [Procedura: Pulire una compilazione](how-to-clean-a-build.md)
#### [Procedura: Fare riferimento a un SDK di progetto MSBuild](how-to-use-project-sdk.md)
### [Attività MSBuild](msbuild-tasks.md)
#### [Scrittura di attività](task-writing.md)
#### [Procedura: Ignorare gli errori nelle attività](how-to-ignore-errors-in-tasks.md)
#### [Procedura: Compilare un progetto con risorse](how-to-build-a-project-that-has-resources.md)
#### [Attività inline di MSBuild](msbuild-inline-tasks.md)
##### [Procedura dettagliata: creazione di un'attività inline](walkthrough-creating-an-inline-task.md)
### [Confronto di proprietà ed elementi](comparing-properties-and-items.md)
### [Caratteri speciali di MSBuild](msbuild-special-characters.md)
#### [Procedura: Eseguire caratteri speciali di escape in MSBuild](how-to-escape-special-characters-in-msbuild.md)
#### [Procedura: Usare caratteri XML riservati nei file di progetto](how-to-use-reserved-xml-characters-in-project-files.md)
## [Concetti avanzati relativi a MSBuild](msbuild-advanced-concepts.md)
### [Batch MSBuild](msbuild-batching.md)
#### [Metadati degli elementi in batch delle attività](item-metadata-in-task-batching.md)
#### [Metadati degli elementi nell'esecuzione in batch delle destinazioni](item-metadata-in-target-batching.md)
### [Trasformazioni di MSBuild](msbuild-transforms.md)
### [Integrazione di Visual Studio (MSBuild)](visual-studio-integration-msbuild.md)
#### [Procedura: Estendere il processo di compilazione di Visual Studio](how-to-extend-the-visual-studio-build-process.md)
#### [Avvio di una compilazione all'interno dell'IDE](starting-a-build-from-within-the-ide.md)
#### [Registrazione di estensioni di .NET Framework](registering-extensions-of-the-dotnet-framework.md)
### [Compilazione di più progetti in parallelo con MSBuild](building-multiple-projects-in-parallel-with-msbuild.md)
#### [Uso di più processori per la compilazione di progetti](using-multiple-processors-to-build-projects.md)
#### [Uso efficiente della memoria nella compilazione di progetti di grandi dimensioni](using-memory-efficiently-when-you-build-large-projects.md)
### [Panoramica del multitargeting di MSBuild](msbuild-multitargeting-overview.md)
#### [Set di strumenti di MSBuild (ToolsVersion)](msbuild-toolset-toolsversion.md)
##### [Configurazioni standard e personalizzate del set di strumenti](standard-and-custom-toolset-configurations.md)
##### [Override delle impostazioni ToolsVersion](overriding-toolsversion-settings.md)
#### [Framework e piattaforma di destinazione di MSBuild](msbuild-target-framework-and-target-platform.md)
#### [Risoluzione di assembly in fase di progettazione](resolving-assemblies-at-design-time.md)
#### [Configurazione di destinazioni e attività](configuring-targets-and-tasks.md)
##### [Procedura: Configurare destinazioni e attività](how-to-configure-targets-and-tasks.md)
#### [Risoluzione dei problemi relativi agli errori di impostazione di .NET Framework come destinazione](troubleshooting-dotnet-framework-targeting-errors.md)
### [Personalizzare la compilazione](customize-your-build.md)
### [Procedure consigliate di MSBuild](msbuild-best-practices.md)
## [Registrazione a MSBuild](logging-in-msbuild.md)
### [Recupero di log di compilazione con MSBuild](obtaining-build-logs-with-msbuild.md)
### [Logger di compilazione](build-loggers.md)
### [Registrazione in un ambiente a più processori](logging-in-a-multi-processor-environment.md)
### [Scrittura di logger compatibili con più processori](writing-multi-processor-aware-loggers.md)
### [Creazione di logger di inoltro](creating-forwarding-loggers.md)
## [Procedura dettagliata: uso di MSBuild](walkthrough-using-msbuild.md)
## [Procedura dettagliata: creazione di un nuovo file di progetto MSBuild](walkthrough-creating-an-msbuild-project-file-from-scratch.md)
## [Riferimenti a MSBuild](msbuild-reference.md)
### [Riferimenti dello schema del file di progetto MSBuild](msbuild-project-file-schema-reference.md)
#### [Elemento Choose (MSBuild)](choose-element-msbuild.md)
#### [Elemento Import (MSBuild)](import-element-msbuild.md)
#### [Elemento ImportGroup](importgroup-element.md)
#### [Elemento Item (MSBuild)](item-element-msbuild.md)
#### [Elemento ItemDefinitionGroup (MSBuild)](itemdefinitiongroup-element-msbuild.md)
#### [Elemento ItemGroup (MSBuild)](itemgroup-element-msbuild.md)
#### [Elemento ItemMetadata (MSBuild)](itemmetadata-element-msbuild.md)
#### [Elemento OnError (MSBuild)](onerror-element-msbuild.md)
#### [Elemento Otherwise (MSBuild)](otherwise-element-msbuild.md)
#### [Elemento Output (MSBuild)](output-element-msbuild.md)
#### [Elemento Parameter](parameter-element.md)
#### [ParameterGroup (elemento)](parametergroup-element.md)
#### [Elemento Project (MSBuild)](project-element-msbuild.md)
#### [Elemento ProjectExtensions (MSBuild)](projectextensions-element-msbuild.md)
#### [Elemento Property (MSBuild)](property-element-msbuild.md)
#### [Elemento PropertyGroup (MSBuild)](propertygroup-element-msbuild.md)
#### [Elemento Sdk (MSBuild)](sdk-element-msbuild.md)
#### [Elemento Target (MSBuild)](target-element-msbuild.md)
#### [Elemento Task (MSBuild)](task-element-msbuild.md)
#### [Elemento TaskBody (MSBuild)](taskbody-element-msbuild.md)
#### [Elemento UsingTask (MSBuild)](usingtask-element-msbuild.md)
#### [Elemento When (MSBuild)](when-element-msbuild.md)
### [Riferimenti delle attività MSBuild](msbuild-task-reference.md)
#### [Attività MSBuild specifiche di Visual C++](msbuild-tasks-specific-to-visual-cpp.md)
##### [Attività BscMake](bscmake-task.md)
##### [Attività CL](cl-task.md)
##### [Attività CPPClean](cppclean-task.md)
##### [Attività LIB](lib-task.md)
##### [Attività Link](link-task.md)
##### [Attività MIDL](midl-task.md)
##### [Attività MT](mt-task.md)
##### [Attività RC](rc-task.md)
##### [Attività SetEnv](setenv-task.md)
##### [Attività VCMessage](vcmessage-task.md)
##### [Attività XDCMake](xdcmake-task.md)
##### [Attività XSD](xsd-task.md)
#### [Classe di base Task](task-base-class.md)
#### [Classe di base TaskExtension](taskextension-base-class.md)
#### [Classe di base ToolTaskExtension](tooltaskextension-base-class.md)
#### [Attività AL (Assembly Linker)](al-assembly-linker-task.md)
#### [Attività AspNetCompiler](aspnetcompiler-task.md)
#### [Attività AssignCulture](assignculture-task.md)
#### [Attività AssignProjectConfiguration](assignprojectconfiguration-task.md)
#### [Attività AssignTargetPath](assigntargetpath-task.md)
#### [Attività CallTarget](calltarget-task.md)
#### [Attività CombinePath](combinepath-task.md)
#### [Attività ConvertToAbsolutePath](converttoabsolutepath-task.md)
#### [Attività Copy](copy-task.md)
#### [Attività CreateCSharpManifestResourceName](createcsharpmanifestresourcename-task.md)
#### [Attività CreateItem](createitem-task.md)
#### [Attività CreateProperty](createproperty-task.md)
#### [Attività CreateVisualBasicManifestResourceName](createvisualbasicmanifestresourcename-task.md)
#### [Attività Csc](csc-task.md)
#### [Attività Delete](delete-task.md)
#### [Attività Error](error-task.md)
#### [Attività Exec](exec-task.md)
#### [Attività FindAppConfigFile](findappconfigfile-task.md)
#### [Attività FindInList](findinlist-task.md)
#### [Attività FindUnderPath](findunderpath-task.md)
#### [Attività FormatUrl task](formaturl-task.md)
#### [Attività FormatVersion](formatversion-task.md)
#### [Attività GenerateApplicationManifest](generateapplicationmanifest-task.md)
#### [Attività GenerateBootstrapper](generatebootstrapper-task.md)
#### [Attività GenerateDeploymentManifest](generatedeploymentmanifest-task.md)
#### [Attività GenerateResource](generateresource-task.md)
#### [Attività GenerateTrustInfo](generatetrustinfo-task.md)
#### [Attività GetAssemblyIdentity](getassemblyidentity-task.md)
#### [Attività GetFrameworkPath](getframeworkpath-task.md)
#### [Attività GetFrameworkSdkPath](getframeworksdkpath-task.md)
#### [Attività GetReferenceAssemblyPaths](getreferenceassemblypaths-task.md)
#### [Attività LC](lc-task.md)
#### [Attività MakeDir](makedir-task.md)
#### [Attività Message](message-task.md)
#### [Attività Move](move-task.md)
#### [Attività MSBuild](msbuild-task.md)
#### [Attività ReadLinesFromFile](readlinesfromfile-task.md)
#### [Attività RegisterAssembly](registerassembly-task.md)
#### [Attività RemoveDir](removedir-task.md)
#### [Attività RemoveDuplicates](removeduplicates-task.md)
#### [Attività RequiresFramework35SP1Assembly](requiresframework35sp1assembly-task.md)
#### [Attività ResolveAssemblyReference](resolveassemblyreference-task.md)
#### [Attività ResolveComReference](resolvecomreference-task.md)
#### [Attività ResolveKeySource](resolvekeysource-task.md)
#### [Attività ResolveManifestFiles](resolvemanifestfiles-task.md)
#### [Attività ResolveNativeReference](resolvenativereference-task.md)
#### [Attività ResolveNonMSBuildProjectOutput](resolvenonmsbuildprojectoutput-task.md)
#### [Attività SGen](sgen-task.md)
#### [Attività SignFile](signfile-task.md)
#### [Attività Touch](touch-task.md)
#### [Attività UnregisterAssembly](unregisterassembly-task.md)
#### [Attività UpdateManifest](updatemanifest-task.md)
#### [Attività Vbc](vbc-task.md)
#### [Attività Warning](warning-task.md)
#### [Attività WriteCodeFragment](writecodefragment-task.md)
#### [Attività WriteLinesToFile](writelinestofile-task.md)
#### [Attività XmlPeek](xmlpeek-task.md)
#### [XmlPoke Task](xmlpoke-task.md)
#### [Attività XslTransformation](xsltransformation-task.md)
### [Condizioni di MSBuild](msbuild-conditions.md)
### [Costrutti condizionali di MSBuild](msbuild-conditional-constructs.md)
### [Proprietà riservate e note MSBuild](msbuild-reserved-and-well-known-properties.md)
### [Proprietà di progetto MSBuild comuni](common-msbuild-project-properties.md)
### [Elementi di progetto MSBuild comuni](common-msbuild-project-items.md)
### [Riferimenti alla riga di comando di MSBuild](msbuild-command-line-reference.md)
### [File con estensione targets di MSBuild](msbuild-dot-targets-files.md)
### [Metadati noti degli elementi di MSBuild](msbuild-well-known-item-metadata.md)
### [File di risposta MSBuild](msbuild-response-files.md)
### [Informazioni di riferimento su MSBuild WPF](wpf-msbuild-reference.md)
#### [File WPF con estensione targets](wpf-dot-targets-files.md)
#### [Informazioni di riferimento sulle attività MSBuild WPF](wpf-msbuild-task-reference.md)
##### [Attività FileClassifier](fileclassifier-task.md)
##### [Attività GenerateTemporaryTargetAssembly](generatetemporarytargetassembly-task.md)
##### [Attività GetWinFXPath](getwinfxpath-task.md)
##### [Attività MarkupCompilePass1](markupcompilepass1-task.md)
##### [Attività MarkupCompilePass2](markupcompilepass2-task.md)
##### [Attività MergeLocalizationDirectives](mergelocalizationdirectives-task.md)
##### [Attività ResourcesGenerator](resourcesgenerator-task.md)
##### [Attività UidManager](uidmanager-task.md)
##### [Attività UpdateManifestForBrowserApplication](updatemanifestforbrowserapplication-task.md)
### [Caratteri speciali di escape](special-characters-to-escape.md)
## [Glossario di MSBuild](msbuild-glossary.md)
