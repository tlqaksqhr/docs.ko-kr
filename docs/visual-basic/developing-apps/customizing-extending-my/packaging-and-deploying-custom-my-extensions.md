---
title: "Packaging and Deploying Custom My Extensions (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My namespace, customizing"
  - "My namespace"
  - "My namespace, extending"
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Packaging and Deploying Custom My Extensions (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Visual Basic에서는 Visual Studio 템플릿을 사용하여 사용자 지정 `My` 네임스페이스 확장을 간편하게 배포할 수 있습니다.  `My` 확장이 새 프로젝트 형식의 중요 부분인 프로젝트 템플릿을 만드는 경우 템플릿을 내보낼 때 프로젝트에 사용자 지정 `My` 확장 코드를 포함할 수 있습니다.  프로젝트 템플릿 내보내기에 대한 자세한 내용은 [방법: 프로젝트 템플릿 만들기](../Topic/How%20to:%20Create%20Project%20Templates.md)를 참조하십시오.  
  
 사용자 지정 `My` 확장이 하나의 코드 파일에 들어 있는 경우 파일을 모든 종류의 Visual Basic 프로젝트에 추가할 수 있는 항목 템플릿으로 내보낼 수 있습니다.  그런 다음 항목 템플릿을 사용자 지정하여 Visual Basic 프로젝트에서 사용자 지정 `My` 확장에 대한 추가적인 기능 및 동작을 설정할 수 있습니다.  다음과 같은 기능이 포함됩니다.  
  
-   사용자가 Visual Basic 프로젝트 디자이너의 **My 확장** 페이지에서 사용자 지정 `My` 확장을 관리할 수 있게 하는 기능  
  
-   지정된 어셈블리에 대한 참조가 프로젝트에 추가될 때 사용자 지정 `My` 확장을 자동으로 추가하는 기능  
  
-   `My` 확장 항목 템플릿이 프로젝트 항목 목록에 포함되지 않도록 **항목 추가** 대화 상자에서 숨기는 기능  
  
 이 단원에서는 사용자 지정 `My` 확장을 Visual Basic 프로젝트 디자이너의 **My 확장** 페이지에서 관리할 수 있는 숨겨진 항목 템플릿으로 패키징하는 방법을 설명합니다.  지정된 어셈블리에 대한 참조가 프로젝트에 추가될 때 사용자 지정 `My` 확장이 자동으로 추가될 수 있습니다.  
  
## My 네임스페이스 확장 만들기  
 사용자 지정 `My` 확장에 대한 배포 패키지를 만드는 첫 번째 단계는 확장을 하나의 코드 파일로 만드는 것입니다.  사용자 지정 `My` 확장을 만드는 방법에 대한 자세한 내용과 지침은 [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)을 참조하십시오.  
  
## My 네임스페이스 확장을 항목 템플릿으로 내보내기  
 `My` 네임스페이스 확장이 포함된 코드 파일을 만든 뒤에는 코드 파일을 Visual Studio 항목 템플릿으로 내보낼 수 있습니다.  파일을 Visual Studio 항목 템플릿으로 내보내는 방법에 대한 지침은 [방법: 항목 템플릿 만들기](../Topic/How%20to:%20Create%20Item%20Templates.md)를 참조하십시오.  
  
> [!NOTE]
>  `My` 네임스페이스 확장이 특정 어셈블리에 종속된 경우 해당 어셈블리에 대한 참조가 추가될 때 `My` 네임스페이스 확장을 자동으로 설치하도록 항목 템플릿을 사용자 지정할 수 있습니다.  이 경우 코드 파일을 Visual Studio 항목 템플릿으로 내보낼 때 해당 어셈블리 참조를 제외할 수 있습니다.  
  
## 항목 템플릿 사용자 지정  
 항목 템플릿이 Visual Basic 프로젝트 디자이너의 **My 확장** 페이지에서 관리되도록 할 수 있습니다.  또한 지정된 어셈블리에 대한 참조가 프로젝트에 추가되었을 때 자동으로 항목 템플릿이 추가되도록 할 수도 있습니다.  이러한 사용자 지정 기능을 설정하려면 템플릿에 CustomData 파일이라는 새 파일을 추가한 다음 .vstemplate 파일에 XML에 대한 새 요소를 추가해야 합니다.  
  
### CustomData 파일 추가  
 CustomData 파일은 파일 확장명이 .CustomData이며 XML을 포함하는 텍스트 파일입니다. 파일 이름은 템플릿을 잘 설명하는 값으로 설정할 수 있습니다.  CustomData 파일의 XML은 사용자가 Visual Basic 프로젝트 디자이너의 **My 확장** 페이지를 사용할 때 `My` 확장을 포함하도록 Visual Basic에 지시합니다.  원하는 경우 \<`AssemblyFullName>` 특성을 CustomData 파일 XML에 추가할 수 있습니다.  이렇게 하면 특정 어셈블리에 대한 참조가 프로젝트에 추가될 때 Visual Basic이 자동으로 사용자 지정 `My` 확장을 설치합니다.  원하는 텍스트 편집기 또는 XML 편집기를 사용하여 CustomData 파일을 만든 다음 이 파일을 항목 템플릿의 압축 폴더\(.zip 파일\)에 추가할 수 있습니다.  
  
 예를 들어 다음 XML은 Microsoft.VisualBasic.PowerPacks.Vs.dll 어셈블리에 대한 참조가 프로젝트에 추가되었을 때 템플릿 항목을 Visual Basic 프로젝트의 My 확장 폴더에 추가하는 CustomData 파일의 내용을 보여 줍니다.  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 CustomData 파일에는 \<`VBMyExtensionTemplate>` 요소가 들어 있으며 이 요소에는 다음 표에 나열된 특성이 사용됩니다.  
  
|||  
|-|-|  
|특성|설명|  
|`ID`|필수 요소.  확장의 고유한 식별자입니다.  이 ID를 갖는 확장이 이미 프로젝트에 추가된 경우에는 다시 추가하라는 메시지가 나타나지 않습니다.|  
|`Version`|필수 요소.  항목 템플릿의 버전 번호입니다.|  
|`AssemblyFullName`|선택적 요소.  어셈블리 이름입니다.  이 어셈블리에 대한 참조가 프로젝트에 추가되면 이 항목 템플릿에서 `My` 확장을 추가하라는 메시지가 사용자에게 표시됩니다.|  
  
### .vstemplate 파일에 \<CustomDataSignature\> 요소 추가  
 Visual Studio 항목 템플릿을 `My` 네임스페이스 확장으로 식별하려면 항목 템플릿에 대한 .vstemplate 파일도 수정해야 합니다.  `<CustomDataSignature>` 요소를 `<TemplateData>` 요소에 추가해야 합니다.  다음 예제에서처럼 `<CustomDataSignature>` 요소에는 `Microsoft.VisualBasic.MyExtension`이라는 텍스트가 포함되어야 합니다.  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 압축 폴더\(.zip 파일\)에 있는 파일은 직접 수정할 수 없습니다.  압축 폴더에서 .vstemplate 파일을 복사하고, 수정한 다음 압축 폴더의 .vstemplate 파일을 업데이트된 복사본으로 바꿔야 합니다.  
  
 다음 예제에서는 `<CustomDataSignature>` 요소가 추가된 .vstemplate 파일의 내용을 보여 줍니다.  
  
```  
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
  <TemplateData>  
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>  
    <Name>MyPrinterInfo</Name>  
    <Description>Custom My Extensions Item Template</Description>  
    <ProjectType>VisualBasic</ProjectType>  
    <SortOrder>10</SortOrder>  
    <Icon>__TemplateIcon.ico</Icon>  
    <CustomDataSignature       >Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
  </TemplateData>  
  <TemplateContent>  
    <References />  
    <ProjectItem SubType="Code"   
                 TargetFileName="$fileinputname$.vb"  
                 ReplaceParameters="true"  
     >MyCustomExtensionModule.vb</ProjectItem>  
  </TemplateContent>  
</VSTemplate>  
```  
  
## 템플릿 설치  
 템플릿을 설치하려면 압축 폴더\(.zip 파일\)를 Visual Basic 항목 템플릿 폴더\(예를 들어 My Documents\\Visual Studio 2008\\Templates\\Item Templates\\Visual Basic\)에 복사합니다.  또는 템플릿을 Visual Studio 설치 관리자 파일\(.vsi\)로 게시할 수도 있습니다.  템플릿을 Visual Studio 설치 관리자 파일로 게시하는 방법에 대한 내용은 [NIB: How to: Publish Project Templates](http://msdn.microsoft.com/ko-kr/b9087f58-64e9-4767-bf54-e3bf40d63b20)를 참조하십시오.  
  
## 참고 항목  
 [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)   
 [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [프로젝트 디자이너, My 확장 페이지](/visual-studio/ide/reference/my-extensions-page-project-designer-visual-basic)