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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 81483722227873d1b145219ae5c4326d841ff876
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a><span data-ttu-id="40335-102">패키징 및 배포 사용자 지정 My 확장 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="40335-102">Packaging and deploying custom My extensions (Visual Basic)</span></span>
<span data-ttu-id="40335-103">Visual Basic에서 사용자 지정을 배포할 수 있는 쉬운 방법을 제공 `My` Visual Studio 템플릿을 사용 하 여 네임 스페이스 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="40335-104">프로젝트 서식 파일을 만드는 경우 사용자 `My` 확장은 새 프로젝트 종류의 필수적인 부분, 사용자 지정 포함할 수 있습니다 `My` 템플릿을 내보낼 때 프로젝트를 사용 하 여 확장 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="40335-105">프로젝트 템플릿 내보내기에 대 한 자세한 내용은 참조 [하는 방법: 프로젝트 템플릿 만들기](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398)합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-105">For more information about exporting project templates, see [How to: Create Project Templates](http://msdn.microsoft.com/library/a1a6999d-a34c-48a8-b1cf-027eb5c76398).</span></span>  
  
 <span data-ttu-id="40335-106">하는 경우 사용자 지정 `My` 확장은 단일 코드 파일에서 사용자가 모든 종류의 Visual Basic 프로젝트에 추가할 수 있는 항목 템플릿으로 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="40335-107">다음 추가 기능 및 사용자 지정에 대 한 동작을 사용 하도록 항목 템플릿을 사용자 지정할 수 `My` Visual Basic 프로젝트에서 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="40335-108">이러한 기능에는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-108">Those capabilities include the following:</span></span>  
  
-   <span data-ttu-id="40335-109">사용자가 사용자 지정을 관리할 수 있도록 `My` 에서 확장 된 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>  
  
-   <span data-ttu-id="40335-110">사용자 지정을 자동으로 추가 `My` 확장 때 지정된 된 어셈블리에 대 한 참조를 프로젝트에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40335-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>  
  
-   <span data-ttu-id="40335-111">숨기는 `My` 에서 확장 항목 템플릿이 **항목 추가** 대화 상자를 프로젝트 항목의 목록에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>  
  
 <span data-ttu-id="40335-112">이 항목에서는 사용자 지정 패키지 하는 방법을 설명 `My` 확장에서 관리할 수 있는 숨겨진된 항목 템플릿으로 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="40335-113">사용자 지정 `My` 지정된 된 어셈블리에 대 한 참조를 프로젝트에 추가 될 때 확장이 자동으로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>  
  
## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="40335-114">만들기는 My 네임 스페이스 확장</span><span class="sxs-lookup"><span data-stu-id="40335-114">Create a My namespace extension</span></span>  
 <span data-ttu-id="40335-115">사용자 지정에 대 한 배포 패키지를 만드는 첫 번째 단계는 `My` 확장은 단일 코드 파일로 확장을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="40335-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="40335-116">자세한 내용 및 사용자 지정을 만드는 방법에 대 한 지침은 `My` 확장 참조 [Visual Basic에서 My Namespace 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="40335-117">내보내기는 항목 템플릿과 My 네임 스페이스 확장</span><span class="sxs-lookup"><span data-stu-id="40335-117">Export a My namespace extension as an item template</span></span>  
 <span data-ttu-id="40335-118">포함 된 코드 파일을 만든 후에 `My` 네임 스페이스 확장을 Visual Studio 항목 템플릿으로 코드 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="40335-119">Visual Studio 항목 템플릿 파일을 내보내는 방법에 대 한 지침을 참조 하십시오. [하는 방법: 항목 템플릿 만들기](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5)합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](http://msdn.microsoft.com/library/77bc53d4-d607-4820-a032-7e3b365891b5).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="40335-120">경우에 `My` 네임 스페이스 확장에 특정 어셈블리에 대 한 종속성을 자동으로 설치 하도록 항목 템플릿을 사용자 지정할 수 있습니다 프로그램 `My` 해당 어셈블리에 대 한 참조가 추가 되 면 네임 스페이스 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="40335-121">결과적으로, Visual Studio 항목 템플릿 코드 파일을 내보낼 때 해당 어셈블리 참조를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>  
  
## <a name="customize-the-item-template"></a><span data-ttu-id="40335-122">항목 템플릿 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="40335-122">Customize the item template</span></span>  
 <span data-ttu-id="40335-123">관리 하도록 항목 템플릿을 사용 하도록 설정할 수는 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="40335-124">지정된 된 어셈블리에 대 한 참조를 프로젝트에 추가 되 면 자동으로 추가 될 항목 템플릿을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="40335-125">이러한 사용자 지정을 사용 하도록 설정 하 여 템플릿에 CustomData 파일 이라는 새 파일을 추가 한 다음.vstemplate 파일의 XML에 새 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>  
  
### <a name="add-the-customdata-file"></a><span data-ttu-id="40335-126">CustomData 파일 추가</span><span class="sxs-lookup"><span data-stu-id="40335-126">Add the CustomData file</span></span>  
 <span data-ttu-id="40335-127">CustomData 파일이 텍스트 파일의 파일 이름 확장명이 있는 경우 CustomData (파일 이름으로 설정할 수는 모든 값 서식 파일에 의미 있는) XML을 포함 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="40335-128">CustomData 파일에서에서 XML을 포함 하도록 Visual Basic에 지시 하면 `My` 사용자가 사용할 때 확장은 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="40335-129">선택적으로 추가할 수는 `AssemblyFullName>` CustomData 파일 XML 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="40335-130">이렇게 하면 자동으로 사용자 지정을 설치 하려면 Visual Basic `My` 확장 때 특정 어셈블리에 대 한 참조를 프로젝트에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="40335-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="40335-131">CustomData 파일을 만들려면 원하는 텍스트 편집기 또는 XML 편집기를 사용할 수 있고 항목 서식 파일의 압축 된 폴더 (.zip 파일)에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>  
  
 <span data-ttu-id="40335-132">예를 들어, 다음 XML에서는 때 Microsoft.VisualBasic.PowerPacks.Vs.dll 어셈블리에 대 한 Visual Basic 프로젝트의 My 확장 폴더에는 템플릿 항목을 추가 하는 CustomData 파일의 내용을 프로젝트에 추가 됩니다 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="40335-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>  
  
```  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 <span data-ttu-id="40335-133">CustomData 파일에는 `VBMyExtensionTemplate>` 다음 표에 나열 된 특성이 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>  
  
|<span data-ttu-id="40335-134">특성</span><span class="sxs-lookup"><span data-stu-id="40335-134">Attribute</span></span>|<span data-ttu-id="40335-135">설명</span><span class="sxs-lookup"><span data-stu-id="40335-135">Description</span></span>|  
|---|---|  
|`ID`|<span data-ttu-id="40335-136">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="40335-136">Required.</span></span> <span data-ttu-id="40335-137">확장에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-137">A unique identifier for the extension.</span></span> <span data-ttu-id="40335-138">이 ID를 갖는 확장 프로젝트에 이미 추가 되었습니다 다시 추가 하는 사용자 묻지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|  
|`Version`|<span data-ttu-id="40335-139">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="40335-139">Required.</span></span> <span data-ttu-id="40335-140">항목 템플릿에 대 한 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-140">A version number for the item template.</span></span>|  
|`AssemblyFullName`|<span data-ttu-id="40335-141">선택적 요소.</span><span class="sxs-lookup"><span data-stu-id="40335-141">Optional.</span></span> <span data-ttu-id="40335-142">어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-142">An assembly name.</span></span> <span data-ttu-id="40335-143">이 어셈블리에 대 한 참조를 프로젝트에 추가 되는 메시지가 표시 됩니다 추가 하 여 `My` 항목 템플릿을 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="40335-144">추가 된 \<CustomDataSignature > 요소를.vstemplate 파일</span><span class="sxs-lookup"><span data-stu-id="40335-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>  
 <span data-ttu-id="40335-145">Visual Studio 항목 템플릿을으로 식별 하는 `My` 네임 스페이스 확장 항목 템플릿에 대 한.vstemplate 파일을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="40335-146">추가 해야는 `<CustomDataSignature>` 요소에는 `<TemplateData>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="40335-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="40335-147">`<CustomDataSignature>` 요소는 텍스트를 포함 해야 `Microsoft.VisualBasic.MyExtension`다음 예제와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>  
  
```  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 <span data-ttu-id="40335-148">압축 된 폴더 (.zip 파일)의 파일을 직접 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="40335-149">압축된 된 폴더에서.vstemplate 파일을 복사, 수정, 하 고 압축된 폴더의.vstemplate 파일에 업데이트 된 복사본을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="40335-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>  
  
 <span data-ttu-id="40335-150">다음 예제에서는 있는.vstemplate 파일의 내용을 `<CustomDataSignature>` 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="40335-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>  
  
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
  
## <a name="install-the-template"></a><span data-ttu-id="40335-151">서식 파일 설치</span><span class="sxs-lookup"><span data-stu-id="40335-151">Install the template</span></span>  
 <span data-ttu-id="40335-152">서식 파일을 설치 하려면 (예를 들어 My Documents\Visual Studio 2008\Templates\Item Templates\Visual 기본) Visual Basic 항목 템플릿 폴더에 압축된 된 폴더 (.zip 파일)를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-152">To install the template, you can copy the compressed folder (.zip file) to the Visual Basic item templates folder (for example, My Documents\Visual Studio 2008\Templates\Item Templates\Visual Basic).</span></span> <span data-ttu-id="40335-153">또는 Visual Studio 설치 관리자 (.vsi) 파일로 서식 파일을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40335-153">Alternatively, you can publish the template as a Visual Studio Installer (.vsi) file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40335-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40335-154">See also</span></span>  
 <span data-ttu-id="40335-155">[확장은 Visual Basic에서 My Namespace](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="40335-155">[Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md) </span></span>  
<span data-ttu-id="40335-156"> [Visual Basic 응용 프로그램 모델 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md) </span><span class="sxs-lookup"><span data-stu-id="40335-156"> [Extending the Visual Basic Application Model](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md) </span></span>  
<span data-ttu-id="40335-157"> [사용자 지정 하는 개체는 지원 되는 내](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md) </span><span class="sxs-lookup"><span data-stu-id="40335-157"> [Customizing Which Objects are Available in My](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md) </span></span>  
<span data-ttu-id="40335-158"> [프로젝트 디자이너, my 확장 페이지](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="40335-158"> [My Extensions Page, Project Designer](https://docs.microsoft.com/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)</span></span>
