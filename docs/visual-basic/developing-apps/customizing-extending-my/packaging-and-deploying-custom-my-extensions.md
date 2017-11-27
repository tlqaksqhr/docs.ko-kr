---
title: "패키징 및 배포 사용자 지정 My 확장명 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- My namespace [Visual Basic], customizing
- My namespace
- My namespace [Visual Basic], extending
ms.assetid: fd89c54b-0290-4c50-95a3-ff17d4487a21
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94a9ea977d0add14ae9f0c9a889b008b94610ee0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="packaging-and-deploying-custom-my-extensions-visual-basic"></a><span data-ttu-id="0a278-102">패키징 및 배포 사용자 지정 My 확장명 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a278-102">Packaging and deploying custom My extensions (Visual Basic)</span></span>
<span data-ttu-id="0a278-103">Visual Basic에서 사용자 지정을 배포할 수 있는 쉬운 방법을 제공 `My` Visual Studio 템플릿을 사용 하 여 네임 스페이스 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-103">Visual Basic provides an easy way for you to deploy your custom `My` namespace extensions by using Visual Studio templates.</span></span> <span data-ttu-id="0a278-104">프로젝트 템플릿을를 만드는 경우 사용자 `My` 확장은 새 프로젝트 형식의 필수적인 부분, 사용자 지정 포함할 수 있습니다 `My` 템플릿을 내보낼 때 프로젝트를 사용 하 여 확장 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-104">If you are creating a project template for which your `My` extensions are an integral part of the new project type, you can just include your custom `My` extension code with the project when you export the template.</span></span> <span data-ttu-id="0a278-105">프로젝트 템플릿 내보내기에 대 한 자세한 내용은 참조 [하는 방법: 프로젝트 템플릿 만들기](/visualstudio/ide/how-to-create-project-templates)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-105">For more information about exporting project templates, see [How to: Create Project Templates](/visualstudio/ide/how-to-create-project-templates).</span></span>  
  
 <span data-ttu-id="0a278-106">하는 경우 사용자 지정 `My` 확장은 단일 코드 파일에서 사용자가 모든 종류의 Visual Basic 프로젝트에 추가할 수 있는 항목 템플릿으로 파일을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-106">If your custom `My` extension is in a single code file, you can export the file as an item template that users can add to any type of Visual Basic project.</span></span> <span data-ttu-id="0a278-107">항목 템플릿을 추가 기능 및 사용자 지정에 대 한 동작을 사용 하도록 설정 하려면 다음 사용자 지정할 수 있습니다 `My` Visual Basic 프로젝트에서 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-107">You can then customize the item template to enable additional capabilities and behavior for your custom `My` extension in a Visual Basic project.</span></span> <span data-ttu-id="0a278-108">이러한 기능에는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-108">Those capabilities include the following:</span></span>  
  
-   <span data-ttu-id="0a278-109">사용자가 사용자 지정을 관리할 수 있도록 `My` 에서 확장의 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-109">Allowing users to manage your custom `My` extension from the **My Extensions** page of the Visual Basic Project Designer.</span></span>  
  
-   <span data-ttu-id="0a278-110">사용자 지정을 자동으로 추가 `My` 확장이 때 지정된 된 어셈블리에 대 한 참조를 프로젝트에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-110">Automatically adding your custom `My` extension when a reference to a specified assembly is added to a project.</span></span>  
  
-   <span data-ttu-id="0a278-111">숨기는 `My` 에서 확장 항목 템플릿이 **항목 추가** 대화 상자를 프로젝트 항목의 목록에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-111">Hiding the `My` extension item template in the **Add Item** dialog box so that it is not included in the list of project items.</span></span>  
  
 <span data-ttu-id="0a278-112">이 항목에서는 사용자 지정 패키지 하는 방법을 설명 `My` 확장에서 관리할 수 있는 숨겨진된 항목 템플릿으로 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-112">This topic discusses how to package a custom `My` extension as a hidden item template that can be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="0a278-113">사용자 지정 `My` 지정된 된 어셈블리에 대 한 참조를 프로젝트에 추가 되 면 확장명이 자동으로 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-113">The custom `My` extension can also be added automatically when a reference to a specified assembly is added to a project.</span></span>  
  
## <a name="create-a-my-namespace-extension"></a><span data-ttu-id="0a278-114">만들기는 My 네임 스페이스 확장</span><span class="sxs-lookup"><span data-stu-id="0a278-114">Create a My namespace extension</span></span>  
 <span data-ttu-id="0a278-115">사용자 지정에 대 한 배포 패키지를 만드는 첫 번째 단계는 `My` 확장은 단일 코드 파일로 확장을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-115">The first step in creating a deployment package for a custom `My` extension is to create the extension as a single code file.</span></span> <span data-ttu-id="0a278-116">자세한 내용 및 지침을 사용자 지정을 만드는 방법에 대 한 `My` 확장 참조 [Visual Basic에서 My Namespace 확장](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-116">For details and guidance about how to create a custom `My` extension, see [Extending the My Namespace in Visual Basic](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md).</span></span>  
  
## <a name="export-a-my-namespace-extension-as-an-item-template"></a><span data-ttu-id="0a278-117">내보내기는 항목 템플릿으로 My 네임 스페이스 확장</span><span class="sxs-lookup"><span data-stu-id="0a278-117">Export a My namespace extension as an item template</span></span>  
 <span data-ttu-id="0a278-118">포함 된 코드 파일을 만들었으면 프로그램 `My` 네임 스페이스 확장 코드 파일을 Visual Studio 항목 템플릿으로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-118">After you have a code file that includes your `My` namespace extension, you can export the code file as a Visual Studio item template.</span></span> <span data-ttu-id="0a278-119">Visual Studio 항목 템플릿 파일을 내보내는 방법에 대 한 지침을 참조 하십시오. [하는 방법: 항목 템플릿 만들기](/visualstudio/ide/how-to-create-item-templates)합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-119">For instructions on how to export a file as a Visual Studio item template, see [How to: Create Item Templates](/visualstudio/ide/how-to-create-item-templates).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a278-120">경우에 `My` 네임 스페이스 확장 특정 어셈블리에 대 한 종속, 자동으로 설치 하도록 항목 템플릿을 사용자 지정할 수 있습니다 프로그램 `My` 해당 어셈블리에 대 한 참조가 추가 되 면 네임 스페이스 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-120">If your `My` namespace extension has a dependency on a particular assembly, you can customize your item template to automatically install your `My` namespace extension when a reference to that assembly is added.</span></span> <span data-ttu-id="0a278-121">결과적으로, 코드 파일을 Visual Studio 항목 템플릿으로 내보낼 때 해당 어셈블리 참조를 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-121">As a result, you will want to exclude that assembly reference when you export the code file as a Visual Studio item template.</span></span>  
  
## <a name="customize-the-item-template"></a><span data-ttu-id="0a278-122">항목 템플릿 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0a278-122">Customize the item template</span></span>  
 <span data-ttu-id="0a278-123">관리 하도록 항목 템플릿을 사용 하도록 설정할 수는 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-123">You can enable your item template to be managed from the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="0a278-124">또한 지정된 된 어셈블리에 대 한 참조를 프로젝트에 추가 될 때 자동으로 추가 될 항목 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-124">You can also enable the item template to be added automatically when a reference to a specified assembly is added to a project.</span></span> <span data-ttu-id="0a278-125">이러한 사용자 지정을 사용 하도록 설정 하려면 CustomData 파일 서식 파일을 호출 하 여 새 파일을 추가 하 고.vstemplate 파일에 새 요소를 XML에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-125">To enable these customizations, you will add a new file, called the CustomData file, to your template, and then add a new element to the XML in your .vstemplate file.</span></span>  
  
### <a name="add-the-customdata-file"></a><span data-ttu-id="0a278-126">CustomData 파일 추가</span><span class="sxs-lookup"><span data-stu-id="0a278-126">Add the CustomData file</span></span>  
 <span data-ttu-id="0a278-127">CustomData 파일이 텍스트 파일의 파일 이름 확장명입니다. CustomData (파일 이름 수 값으로 설정할 수 있는 서식 파일에 의미 있는) XML을 포함 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-127">The CustomData file is a text file that has a file name extension of .CustomData (the file name can be set to any value meaningful to your template) and that contains XML.</span></span> <span data-ttu-id="0a278-128">CustomData 파일의 XML 지시를 포함 하도록 Visual Basic 프로그램 `My` 사용자가 사용할 때 확장의 **My 확장** Visual Basic 프로젝트 디자이너의 페이지입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-128">The XML in the CustomData file instructs Visual Basic to include your `My` extension when users use the **My Extensions** page of the Visual Basic Project Designer.</span></span> <span data-ttu-id="0a278-129">선택적으로 추가할 수는 <`AssemblyFullName>` CustomData 파일 XML 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-129">You can optionally add the <`AssemblyFullName>` attribute to your CustomData file XML.</span></span> <span data-ttu-id="0a278-130">이렇게 하면 자동으로 사용자 지정을 설치 하려면 Visual Basic `My` 확장 때 특정 어셈블리에 대 한 참조는 프로젝트에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-130">This instructs Visual Basic to automatically install your custom `My` extension when a reference to a particular assembly is added to the project.</span></span> <span data-ttu-id="0a278-131">CustomData 파일을 만들려면 원하는 텍스트 편집기 또는 XML 편집기를 사용할 수 있으며 항목 템플릿의 압축된 폴더 (.zip 파일)에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-131">You can use any text editor or XML editor to create the CustomData file, and then add it to your item template's compressed folder (.zip file).</span></span>  
  
 <span data-ttu-id="0a278-132">예를 들어 다음 XML 서식 파일 항목 때 Microsoft.VisualBasic.PowerPacks.Vs.dll 어셈블리에 대 한 Visual Basic 프로젝트의 My 확장 폴더에 추가 될 CustomData 파일의 내용을 프로젝트에 추가 됩니다 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-132">For example, the following XML shows the contents of a CustomData file that will add the template item to the My Extensions folder of a Visual Basic project when a reference to the Microsoft.VisualBasic.PowerPacks.Vs.dll assembly is added to the project.</span></span>  
  
```xml  
<VBMyExtensionTemplate   
    ID="Microsoft.VisualBasic.Samples.MyExtensions.MyPrinterInfo"   
    Version="1.0.0.0"  
    AssemblyFullName="Microsoft.VisualBasic.PowerPacks.vs"  
/>  
```  
  
 <span data-ttu-id="0a278-133">CustomData 파일에는 <`VBMyExtensionTemplate>` 다음 표에 나열 된 특성이 있는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-133">The CustomData file contains a <`VBMyExtensionTemplate>` element that has attributes as listed in the following table.</span></span>  
  
|<span data-ttu-id="0a278-134">특성</span><span class="sxs-lookup"><span data-stu-id="0a278-134">Attribute</span></span>|<span data-ttu-id="0a278-135">설명</span><span class="sxs-lookup"><span data-stu-id="0a278-135">Description</span></span>|  
|---|---|  
|`ID`|<span data-ttu-id="0a278-136">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="0a278-136">Required.</span></span> <span data-ttu-id="0a278-137">확장에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-137">A unique identifier for the extension.</span></span> <span data-ttu-id="0a278-138">이 ID를 갖는 확장 프로젝트에 이미 추가 된 경우 사용자 다시 추가 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-138">If the extension that has this ID has already been added to the project, the user will not be prompted to add it again.</span></span>|  
|`Version`|<span data-ttu-id="0a278-139">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="0a278-139">Required.</span></span> <span data-ttu-id="0a278-140">항목 템플릿에 대 한 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-140">A version number for the item template.</span></span>|  
|`AssemblyFullName`|<span data-ttu-id="0a278-141">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-141">Optional.</span></span> <span data-ttu-id="0a278-142">어셈블리 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-142">An assembly name.</span></span> <span data-ttu-id="0a278-143">이 어셈블리에 대 한 참조는 프로젝트에 추가 되 면 사용자 안내가 제공 됩니다 추가 하 여 `My` 항목 템플릿에서이 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-143">When a reference to this assembly is added to the project, the user will be prompted to add the `My` extension from this item template.</span></span>|  
  
### <a name="add-the-customdatasignature-element-to-the-vstemplate-file"></a><span data-ttu-id="0a278-144">추가 \<CustomDataSignature > 요소를.vstemplate 파일</span><span class="sxs-lookup"><span data-stu-id="0a278-144">Add the \<CustomDataSignature> element to the .vstemplate file</span></span>  
 <span data-ttu-id="0a278-145">와 같이 Visual Studio 항목 템플릿을 식별 하는 `My` 네임 스페이스 확장 항목 템플릿에 대 한.vstemplate 파일을 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-145">To identify your Visual Studio item template as a `My` namespace extension, you must also modify the .vstemplate file for your item template.</span></span> <span data-ttu-id="0a278-146">추가 해야 합니다는 `<CustomDataSignature>` 요소는 `<TemplateData>` 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-146">You must add a `<CustomDataSignature>` element to the `<TemplateData>` element.</span></span> <span data-ttu-id="0a278-147">`<CustomDataSignature>` 요소 텍스트를 포함 해야 `Microsoft.VisualBasic.MyExtension`다음 예제에 나온 것 처럼 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-147">The `<CustomDataSignature>` element must contain the text `Microsoft.VisualBasic.MyExtension`, as shown in the following example.</span></span>  
  
```xml  
<CustomDataSignature>Microsoft.VisualBasic.MyExtension</CustomDataSignature>  
```  
  
 <span data-ttu-id="0a278-148">압축 된 폴더 (.zip 파일)의 파일을 직접 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-148">You cannot modify files in a compressed folder (.zip file) directly.</span></span> <span data-ttu-id="0a278-149">압축 된 폴더에서.vstemplate 파일을 복사, 수정, 하 고 압축 된 폴더에서.vstemplate 파일에 업데이트 된 복사본을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-149">You must copy the .vstemplate file from the compressed folder, modify it, and then replace the .vstemplate file in the compressed folder with your updated copy.</span></span>  
  
 <span data-ttu-id="0a278-150">다음 예제에서는 포함 된.vstemplate 파일의 내용을 보여 줍니다.는 `<CustomDataSignature>` 요소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-150">The following example shows the contents of a .vstemplate file that has the `<CustomDataSignature>` element added.</span></span>  
  
```xml  
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
  
## <a name="install-the-template"></a><span data-ttu-id="0a278-151">서식 파일을 설치</span><span class="sxs-lookup"><span data-stu-id="0a278-151">Install the template</span></span>  
 <span data-ttu-id="0a278-152">서식 파일을 설치 하려면 Visual Basic 항목 템플릿 폴더 (예를 들어 My Documents\Visual Studio 2008\Templates\Item Templates\Visual 기본)에 압축된 폴더 (.zip 파일)를 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-152">To install the template, you can copy the compressed folder (.zip file) to the Visual Basic item templates folder (for example, My Documents\Visual Studio 2008\Templates\Item Templates\Visual Basic).</span></span> <span data-ttu-id="0a278-153">또는 Visual Studio 설치 관리자 (.vsi) 파일로 서식 파일을 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a278-153">Alternatively, you can publish the template as a Visual Studio Installer (.vsi) file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a278-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a278-154">See also</span></span>  
 [<span data-ttu-id="0a278-155">확장은 Visual Basic에서 My Namespace</span><span class="sxs-lookup"><span data-stu-id="0a278-155">Extending the My Namespace in Visual Basic</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-my-namespace.md)  
 [<span data-ttu-id="0a278-156">Visual Basic 응용 프로그램 모델 확장</span><span class="sxs-lookup"><span data-stu-id="0a278-156">Extending the Visual Basic Application Model</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/extending-the-visual-basic-application-model.md)  
 [<span data-ttu-id="0a278-157">My에 사용할 수 있는 개체 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0a278-157">Customizing Which Objects are Available in My</span></span>](../../../visual-basic/developing-apps/customizing-extending-my/customizing-which-objects-are-available-in-my.md)  
 [<span data-ttu-id="0a278-158">프로젝트 디자이너, my 확장 페이지</span><span class="sxs-lookup"><span data-stu-id="0a278-158">My Extensions Page, Project Designer</span></span>](/visualstudio/ide/reference/my-extensions-page-project-designer-visual-basic)
