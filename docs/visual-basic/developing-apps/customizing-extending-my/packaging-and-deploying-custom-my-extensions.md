---
title: "패키징 및 배포 사용자 지정 My 확장 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- My namespace, customizing
- My namespace
- My namespace, extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 950592c0fb197959ce1c3cf6128093846a022709
ms.lasthandoff: 03/13/2017

---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a>패키징 및 배포 사용자 지정 My 확장 (Visual Basic)
Visual Basic에서 사용자 지정을 배포할 수 있는 쉬운 방법을 제공 `My` Visual Studio 템플릿을 사용 하 여 네임 스페이스 확장 합니다. 프로젝트 서식 파일을 만드는 경우 사용자 `My` 확장은 새 프로젝트 종류의 필수적인 부분, 사용자 지정 포함할 수 있습니다 `My` 템플릿을 내보낼 때 프로젝트를 사용 하 여 확장 코드입니다. 프로젝트 템플릿 내보내기에 대 한 자세한 내용은 참조 [하는 방법: 프로젝트 템플릿 만들기](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398)합니다.  
  
 하는 경우 사용자 지정 `My` 확장은 단일 코드 파일에서 사용자가 모든 종류의 Visual Basic 프로젝트에 추가할 수 있는 항목 템플릿으로 파일을 내보낼 수 있습니다. 다음 추가 기능 및 사용자 지정에 대 한 동작을 사용 하도록 항목 템플릿을 사용자 지정할 수 `My` Visual Basic 프로젝트에서 확장 합니다. 이러한 기능에는 다음과 같습니다.  
  
-   사용자가 사용자 지정을 관리할 수 있도록 `My` 에서 확장 된 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다.  
  
-   사용자 지정을 자동으로 추가 `My` 확장 때 지정된 된 어셈블리에 대 한 참조를 프로젝트에 추가 됩니다.  
  
-   숨기는 `My` 에서 확장 항목 템플릿이 **항목 추가** 대화 상자를 프로젝트 항목의 목록에 포함 되지 않습니다.  
  
 이 항목에서는 사용자 지정 패키지 하는 방법을 설명 `My` 확장에서 관리할 수 있는 숨겨진된 항목 템플릿으로 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다. 사용자 지정 `My` 지정된 된 어셈블리에 대 한 참조를 프로젝트에 추가 될 때 확장이 자동으로 추가할 수도 있습니다.  
  
## <a name="create-a-my-namespace-extension"></a>만들기는 My 네임 스페이스 확장  
 사용자 지정에 대 한 배포 패키지를 만드는 첫 번째 단계는 `My` 확장은 단일 코드 파일로 확장을 만듭니다. 자세한 내용 및 사용자 지정을 만드는 방법에 대 한 지침은 `My` 확장 참조 [Visual Basic에서 My Namespace 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)합니다.  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a>내보내기는 항목 템플릿과 My 네임 스페이스 확장  
 포함 된 코드 파일을 만든 후에 `My` 네임 스페이스 확장을 Visual Studio 항목 템플릿으로 코드 파일을 내보낼 수 있습니다. Visual Studio 항목 템플릿 파일을 내보내는 방법에 대 한 지침을 참조 하십시오. [하는 방법: 항목 템플릿 만들기](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5)합니다.  
  
> [!NOTE]
>  경우에 `My` 네임 스페이스 확장에 특정 어셈블리에 대 한 종속성을 자동으로 설치 하도록 항목 템플릿을 사용자 지정할 수 있습니다 프로그램 `My` 해당 어셈블리에 대 한 참조가 추가 되 면 네임 스페이스 확장 합니다. 결과적으로, Visual Studio 항목 템플릿 코드 파일을 내보낼 때 해당 어셈블리 참조를 제외 합니다.  
  
## <a name="customize-the-item-template"></a>항목 템플릿 사용자 지정  
 관리 하도록 항목 템플릿을 사용 하도록 설정할 수는 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다. 지정된 된 어셈블리에 대 한 참조를 프로젝트에 추가 되 면 자동으로 추가 될 항목 템플릿을 사용할 수도 있습니다. 이러한 사용자 지정을 사용 하도록 설정 하 여 템플릿에 CustomData 파일 이라는 새 파일을 추가 한 다음.vstemplate 파일의 XML에 새 요소를 추가 합니다.  
  
### <a name="add-the-customdata-file"></a>CustomData 파일 추가  
 CustomData 파일이 텍스트 파일의 파일 이름 확장명이 있는 경우 CustomData (파일 이름으로 설정할 수는 모든 값 서식 파일에 의미 있는) XML을 포함 하 고 있습니다. CustomData 파일에서에서 XML을 포함 하도록 Visual Basic에 지시 하면 `My` 사용자가 사용할 때 확장은 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다. 선택적으로 추가할 수는 `AssemblyFullName>` CustomData 파일 XML 특성입니다. 이렇게 하면 자동으로 사용자 지정을 설치 하려면 Visual Basic `My` 확장 때 특정 어셈블리에 대 한 참조를 프로젝트에 추가 됩니다. CustomData 파일을 만들려면 원하는 텍스트 편집기 또는 XML 편집기를 사용할 수 있고 항목 서식 파일의 압축 된 폴더 (.zip 파일)에 추가 합니다.  
  
 예를 들어, 다음 XML에서는 때 Microsoft.VisualBasic.PowerPacks.Vs.dll 어셈블리에 대 한 Visual Basic 프로젝트의 My 확장 폴더에는 템플릿 항목을 추가 하는 CustomData 파일의 내용을 프로젝트에 추가 됩니다 보여 줍니다.  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 CustomData 파일에는 `VBMyExtensionTemplate>` 다음 표에 나열 된 특성이 있는 요소입니다.  
  
|특성|설명|  
|---|---|  
|`ID`|필수 요소. 확장에 대 한 고유 식별자입니다. 이 ID를 갖는 확장 프로젝트에 이미 추가 되었습니다 다시 추가 하는 사용자 묻지 않습니다.|  
|`Version`|필수 요소. 항목 템플릿에 대 한 버전 번호입니다.|  
|`AssemblyFullName`|선택적 요소. 어셈블리 이름입니다. 이 어셈블리에 대 한 참조를 프로젝트에 추가 되는 메시지가 표시 됩니다 추가 하 여 `My` 항목 템플릿을 확장 합니다.|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a>추가 된 \<CustomDataSignature > 요소를.vstemplate 파일  
 Visual Studio 항목 템플릿을으로 식별 하는 `My` 네임 스페이스 확장 항목 템플릿에 대 한.vstemplate 파일을 수정 해야 합니다. 추가 해야는 `<CustomDataSignature>` 요소에는 `<TemplateData>` 요소입니다. `<CustomDataSignature>` 요소는 텍스트를 포함 해야 `Microsoft.VisualBasic.MyExtension`다음 예제와 같이 합니다.  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 압축 된 폴더 (.zip 파일)의 파일을 직접 수정할 수 없습니다. 압축된 된 폴더에서.vstemplate 파일을 복사, 수정, 하 고 압축된 폴더의.vstemplate 파일에 업데이트 된 복사본을 바꿉니다.  
  
 다음 예제에서는 있는.vstemplate 파일의 내용을 `<CustomDataSignature>` 요소를 추가 합니다.  
  
```  
<VSTemplate Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" Type="Item">  
  <TemplateData>  
    <DefaultName>MyCustomExtensionModule.vb</DefaultName>  
    <Name>MyPrinterInfo</Name>  
    <Description>Custom My Extensions Item Template</Description>  
    <ProjectType>VisualBasic</ProjectType>  
    <SortOrder>10</SortOrder>  
    <Icon>__TemplateIcon.ico</Icon>  
    <CustomDataSignature      >Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
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
  
## <a name="install-the-template"></a>서식 파일 설치  
 서식 파일을 설치 하려면 (예를 들어 My Documents\Visual Studio 2008\Templates\Item Templates\Visual 기본) Visual Basic 항목 템플릿 폴더에 압축된 된 폴더 (.zip 파일)를 복사할 수 있습니다. 또는 Visual Studio 설치 관리자 (.vsi) 파일로 서식 파일을 게시할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [확장은 Visual Basic에서 My Namespace](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)   
 [Visual Basic 응용 프로그램 모델 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)   
 [사용자 지정 하는 개체는 지원 되는 내](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)   
 [프로젝트 디자이너, my 확장 페이지](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
