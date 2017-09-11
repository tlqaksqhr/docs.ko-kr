---
title: "My.Resources 개체 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
dev_langs:
- VB
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
caps.latest.revision: 22
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
ms.openlocfilehash: 68d0ce69441f18f7a59cb84b0cf363eab9f98669
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="myresources-object"></a><span data-ttu-id="3eade-102">My.Resources 개체</span><span class="sxs-lookup"><span data-stu-id="3eade-102">My.Resources Object</span></span>
<span data-ttu-id="3eade-103">응용 프로그램의 리소스에 액세스 하기 위한 속성 및 클래스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-103">Provides properties and classes for accessing the application's resources.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eade-104">설명</span><span class="sxs-lookup"><span data-stu-id="3eade-104">Remarks</span></span>  
 <span data-ttu-id="3eade-105">`My.Resources` 개체 응용 프로그램의 리소스에 대 한 액세스를 제공 하며, 사용 하면 동적으로 응용 프로그램에 대 한 리소스를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-105">The `My.Resources` object provides access to the application's resources and lets you dynamically retrieve resources for your application.</span></span> <span data-ttu-id="3eade-106">자세한 내용은 참조 [응용 프로그램 리소스 관리 (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet)합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-106">For more information, see [Managing Application Resources (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet).</span></span>  
  
 <span data-ttu-id="3eade-107">`My.Resources` 개체는 전역 리소스에만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-107">The `My.Resources` object exposes only global resources.</span></span> <span data-ttu-id="3eade-108">폼과 관련 된 리소스 파일에 대 한 액세스를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-108">It does not provide access to resource files associated with forms.</span></span> <span data-ttu-id="3eade-109">폼에서 폼 리소스에 액세스 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-109">You must access the form resources from the form.</span></span> <span data-ttu-id="3eade-110">자세한 내용은 [연습: Windows Forms 지역화](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3eade-110">For more information, see [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5).</span></span>  
  
 <span data-ttu-id="3eade-111">응용 프로그램의 문화권 관련 리소스 파일에서 액세스할 수는 `My.Resources` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-111">You can access the application's culture-specific resource files from the `My.Resources` object.</span></span> <span data-ttu-id="3eade-112">기본적으로는 `My.Resources` 개체 culture에 일치 하는 리소스 파일에서 리소스를 찾는 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>속성.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A></span><span class="sxs-lookup"><span data-stu-id="3eade-112">By default, the `My.Resources` object looks up resources from the resource file that matches the culture in the <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> property.</span></span> <span data-ttu-id="3eade-113">그러나이 동작을 재정의할 수 있으며 리소스에 대해 사용 하 여 특정 문화권을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-113">However, you can override this behavior and specify a particular culture to use for the resources.</span></span> <span data-ttu-id="3eade-114">자세한 내용은 참조 [데스크톱 응용 프로그램의 리소스](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890)합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-114">For more information, see [Resources in Desktop Apps](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890).</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3eade-115">속성</span><span class="sxs-lookup"><span data-stu-id="3eade-115">Properties</span></span>  
 <span data-ttu-id="3eade-116">속성은 `My.Resources` 개체는 응용 프로그램의 리소스에 대 한 읽기 전용 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-116">The properties of the `My.Resources` object provide read-only access to your application's resources.</span></span> <span data-ttu-id="3eade-117">를 추가 하거나 리소스를 제거 하는 **프로젝트 디자이너**합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-117">To add or remove resources, use the **Project Designer**.</span></span> <span data-ttu-id="3eade-118">자세한 내용은 참조 [하는 방법: 리소스 추가 또는 제거](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-118">For more information, see [How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).</span></span> <span data-ttu-id="3eade-119">통해 추가 리소스에 액세스할 수는 **프로젝트 디자이너** 를 사용 하 여 `My.Resources.``resourceName`합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-119">You can access resources added through the **Project Designer** by using `My.Resources.``resourceName`.</span></span>  
  
 <span data-ttu-id="3eade-120">추가 하거나에서 프로젝트를 선택 하 여 리소스 파일을 제거할 수도 있습니다 **솔루션 탐색기** 클릭 하 고 **새 항목 추가** 또는 **기존 항목 추가** 에서 **프로젝트** 메뉴.</span><span class="sxs-lookup"><span data-stu-id="3eade-120">You can also add or remove resource files by selecting your project in **Solution Explorer** and clicking **Add New Item** or **Add Existing Item** from the **Project** menu.</span></span> <span data-ttu-id="3eade-121">이 방식으로 사용 하 여 추가 리소스에 액세스할 수 `My.Resources.``resourceFileName`.`resourceName`합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-121">You can access resources added in this manner by using `My.Resources.``resourceFileName`.`resourceName`.</span></span>  
  
 <span data-ttu-id="3eade-122">각 리소스는 이름, 범주 및 값을 포함 하며 이러한 리소스 설정에 따라 리소스를 액세스 하는 속성에 표시 되는 방식을 결정은 `My.Resources` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-122">Each resource has a name, category, and value, and these resource settings determine how the property to access the resource appears in the `My.Resources` object.</span></span> <span data-ttu-id="3eade-123">추가 된 리소스에 대 한는 **프로젝트 디자이너**:</span><span class="sxs-lookup"><span data-stu-id="3eade-123">For resources added in the **Project Designer**:</span></span>  
  
-   <span data-ttu-id="3eade-124">이름, 속성의 이름이 결정</span><span class="sxs-lookup"><span data-stu-id="3eade-124">The name determines the name of the property,</span></span>  
  
-   <span data-ttu-id="3eade-125">리소스 데이터는 속성의 값</span><span class="sxs-lookup"><span data-stu-id="3eade-125">The resource data is the value of the property,</span></span>  
  
-   <span data-ttu-id="3eade-126">범주는 속성의 유형을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-126">The category determines the type of the property:</span></span>  
  
|<span data-ttu-id="3eade-127">범주</span><span class="sxs-lookup"><span data-stu-id="3eade-127">Category</span></span>|<span data-ttu-id="3eade-128">속성 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3eade-128">Property data type</span></span>|  
|---|---|  
|<span data-ttu-id="3eade-129">**문자열**</span><span class="sxs-lookup"><span data-stu-id="3eade-129">**Strings**</span></span>|[<span data-ttu-id="3eade-130">String</span><span class="sxs-lookup"><span data-stu-id="3eade-130">String</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|<span data-ttu-id="3eade-131">**이미지**</span><span class="sxs-lookup"><span data-stu-id="3eade-131">**Images**</span></span>|<span data-ttu-id="3eade-132"><xref:System.Drawing.Bitmap></xref:System.Drawing.Bitmap></span><span class="sxs-lookup"><span data-stu-id="3eade-132"><xref:System.Drawing.Bitmap></span></span>|  
|<span data-ttu-id="3eade-133">**아이콘**</span><span class="sxs-lookup"><span data-stu-id="3eade-133">**Icons**</span></span>|<span data-ttu-id="3eade-134"><xref:System.Drawing.Icon></xref:System.Drawing.Icon></span><span class="sxs-lookup"><span data-stu-id="3eade-134"><xref:System.Drawing.Icon></span></span>|  
|<span data-ttu-id="3eade-135">**오디오**</span><span class="sxs-lookup"><span data-stu-id="3eade-135">**Audio**</span></span>|<span data-ttu-id="3eade-136"><xref:System.IO.UnmanagedMemoryStream></xref:System.IO.UnmanagedMemoryStream></span><span class="sxs-lookup"><span data-stu-id="3eade-136"><xref:System.IO.UnmanagedMemoryStream></span></span><br /><br /> <span data-ttu-id="3eade-137"><xref:System.IO.UnmanagedMemoryStream>클래스에서 파생 되는 <xref:System.IO.Stream>와 같은 스트림를 사용 하는 메서드와 함께 사용할 수 있도록 클래스는 <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>메서드.</xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> </xref:System.IO.Stream> </xref:System.IO.UnmanagedMemoryStream></span><span class="sxs-lookup"><span data-stu-id="3eade-137">The <xref:System.IO.UnmanagedMemoryStream> class derives from the <xref:System.IO.Stream> class, so it can be used with methods that take streams, such as the <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> method.</span></span>|  
|<span data-ttu-id="3eade-138">**파일**</span><span class="sxs-lookup"><span data-stu-id="3eade-138">**Files**</span></span>|<span data-ttu-id="3eade-139">-   [문자열](../../../visual-basic/language-reference/data-types/string-data-type.md) 텍스트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-139">-   [String](../../../visual-basic/language-reference/data-types/string-data-type.md) for text files.</span></span><br /><span data-ttu-id="3eade-140">- <xref:System.Drawing.Bitmap>이미지 파일에 대 한.</xref:System.Drawing.Bitmap></span><span class="sxs-lookup"><span data-stu-id="3eade-140">-   <xref:System.Drawing.Bitmap> for image files.</span></span><br /><span data-ttu-id="3eade-141">- <xref:System.Drawing.Icon>아이콘 파일에 대 한.</xref:System.Drawing.Icon></span><span class="sxs-lookup"><span data-stu-id="3eade-141">-   <xref:System.Drawing.Icon> for icon files.</span></span><br /><span data-ttu-id="3eade-142">- <xref:System.IO.UnmanagedMemoryStream>사운드 파일에 대 한.</xref:System.IO.UnmanagedMemoryStream></span><span class="sxs-lookup"><span data-stu-id="3eade-142">-   <xref:System.IO.UnmanagedMemoryStream> for sound files.</span></span>|  
|<span data-ttu-id="3eade-143">**기타**</span><span class="sxs-lookup"><span data-stu-id="3eade-143">**Other**</span></span>|<span data-ttu-id="3eade-144">디자이너의 정보에 의해 결정 **형식** 열입니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-144">Determined by the information in the designer's **Type** column.</span></span>|  
  
## <a name="classes"></a><span data-ttu-id="3eade-145">클래스</span><span class="sxs-lookup"><span data-stu-id="3eade-145">Classes</span></span>  
 <span data-ttu-id="3eade-146">`My.Resources` 공유 속성을 사용 하 여 클래스와 각 리소스 파일을 노출 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-146">The `My.Resources` object exposes each resource file as a class with shared properties.</span></span> <span data-ttu-id="3eade-147">클래스 이름을 리소스 파일의 이름과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-147">The class name is the same as the name of the resource file.</span></span> <span data-ttu-id="3eade-148">이전 섹션에서 설명한 대로, 리소스 파일의 리소스 클래스에 속성으로 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-148">As described in the previous section, the resources in a resource file are exposed as properties in the class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eade-149">예제</span><span class="sxs-lookup"><span data-stu-id="3eade-149">Example</span></span>  
 <span data-ttu-id="3eade-150">이 예제에서는 폼의 제목 이라는 문자열 리소스가 설정 `Form1Title` 응용 프로그램 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-150">This example sets the title of a form to the string resource named `Form1Title` in the application resource file.</span></span> <span data-ttu-id="3eade-151">이 예제에서 응용 프로그램 이라는 문자열 있어야 `Form1Title` 의 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-151">For the example to work, the application must have a string named `Form1Title` in its resource file.</span></span> <span data-ttu-id="3eade-152">자세한 내용은 참조 [하는 방법: 리소스 추가 또는 제거](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-152">For more information, see [How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).</span></span>  
  
 <span data-ttu-id="3eade-153">[!code-vb[VbVbalrMyResources #&1;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="3eade-153">[!code-vb[VbVbalrMyResources#1](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eade-154">예제</span><span class="sxs-lookup"><span data-stu-id="3eade-154">Example</span></span>  
 <span data-ttu-id="3eade-155">이 예제에서는 명명 된 아이콘을 폼의 아이콘 설정 `Form1Icon` 하는 응용 프로그램의 리소스 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-155">This example sets the icon of the form to the icon named `Form1Icon` that is stored in the application's resource file.</span></span> <span data-ttu-id="3eade-156">이 예제에서에 대 한 응용 프로그램에 있어야 라는 아이콘 `Form1Icon` 의 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-156">For the example to work, the application must have an icon named `Form1Icon` in its resource file.</span></span>  
  
 <span data-ttu-id="3eade-157">[!code-vb[VbVbalrMyResources #&2;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="3eade-157">[!code-vb[VbVbalrMyResources#2](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_2.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eade-158">예제</span><span class="sxs-lookup"><span data-stu-id="3eade-158">Example</span></span>  
 <span data-ttu-id="3eade-159">명명 된 이미지 리소스를 폼의 배경 이미지를 설정 하는이 예제 `Form1Background`, 응용 프로그램 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-159">This example sets the background image of a form to the image resource named `Form1Background`, which is in the application resource file.</span></span> <span data-ttu-id="3eade-160">이 예제가 작동 하려면 응용 프로그램에 있어야 라는 이미지 리소스 `Form1Background` 의 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-160">For this example to work, the application must have an image resource named `Form1Background` in its resource file.</span></span>  
  
 <span data-ttu-id="3eade-161">[!code-vb[VbVbalrMyResources #&3;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="3eade-161">[!code-vb[VbVbalrMyResources#3](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eade-162">예제</span><span class="sxs-lookup"><span data-stu-id="3eade-162">Example</span></span>  
 <span data-ttu-id="3eade-163">이 예제에서는 명명 된 오디오 리소스로 저장 된 소리를 재생 `Form1Greeting` 응용 프로그램의 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-163">This example plays the sound that is stored as an audio resource named `Form1Greeting` in the application's resource file.</span></span> <span data-ttu-id="3eade-164">이 예제에서 응용 프로그램 이라는 오디오 리소스가 있어야 `Form1Greeting` 의 리소스 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-164">For the example to work, the application must have an audio resource named `Form1Greeting` in its resource file.</span></span> <span data-ttu-id="3eade-165">`My.Computer.Audio.Play` 메서드는 Windows Forms 응용 프로그램에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-165">The `My.Computer.Audio.Play` method is available only for Windows Forms applications.</span></span>  
  
 <span data-ttu-id="3eade-166">[!code-vb[VbVbalrMyResources #&4;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="3eade-166">[!code-vb[VbVbalrMyResources#4](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_4.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="3eade-167">예제</span><span class="sxs-lookup"><span data-stu-id="3eade-167">Example</span></span>  
 <span data-ttu-id="3eade-168">이 예에서는 프랑스어 문화권 버전의 응용 프로그램의 문자열 리소스를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-168">This example retrieves the French-culture version of a  string resource of the application.</span></span> <span data-ttu-id="3eade-169">리소스 이름은 `Message`합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-169">The resource is named `Message`.</span></span> <span data-ttu-id="3eade-170">Culture를 변경 하는 `My.Resources` 개체를 사용 하 여,이 예제에서는 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A> 사용</span><span class="sxs-lookup"><span data-stu-id="3eade-170">To change the culture that the `My.Resources` object uses, the example uses <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.</span></span>  
  
 <span data-ttu-id="3eade-171">이 예제가 작동 하려면 응용 프로그램에 있어야 라는 문자열 `Message` 리소스 파일과 응용 프로그램 없어야 Resources.fr-FR.resx 해당 리소스 파일의 프랑스어 문화권 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-171">For this example to work, the application must have a string named `Message` in its resource file, and the application should have the French-culture version of that resource file, Resources.fr-FR.resx.</span></span> <span data-ttu-id="3eade-172">자세한 내용은 참조 [하는 방법: 리소스 추가 또는 제거](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d)합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-172">For more information, see [How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d).</span></span> <span data-ttu-id="3eade-173">응용 프로그램 리소스 파일의 프랑스어 문화권 버전이 없는 경우는 `My.Resource` 개체는 기본 문화권 리소스 파일에서 리소스를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="3eade-173">If the application does not have the French-culture version of the resource file, the `My.Resource` object retrieves the resource from the default-culture resource file.</span></span>  
  
 <span data-ttu-id="3eade-174">[!code-vb[VbVbalrMyResources #&10;](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="3eade-174">[!code-vb[VbVbalrMyResources#10](../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/my-resources-object_5.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eade-175">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3eade-175">See Also</span></span>  
 <span data-ttu-id="3eade-176">[방법: 리소스 추가 또는 제거](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d) </span><span class="sxs-lookup"><span data-stu-id="3eade-176">[How to: Add or Remove Resources](http://msdn.microsoft.com/en-us/7b77bc06-3952-4799-b029-def3f8f7f88d) </span></span>  
<span data-ttu-id="3eade-177"> [응용 프로그램 리소스 (.NET) 관리](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet) </span><span class="sxs-lookup"><span data-stu-id="3eade-177"> [Managing Application Resources (.NET)](https://docs.microsoft.com/visualstudio/ide/managing-application-resources-dotnet) </span></span>  
<span data-ttu-id="3eade-178"> [데스크톱 앱의 리소스](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890) </span><span class="sxs-lookup"><span data-stu-id="3eade-178"> [Resources in Desktop Apps](http://msdn.microsoft.com/library/8ad495d4-2941-40cf-bf64-e82e85825890) </span></span>  
<span data-ttu-id="3eade-179"> [연습: Windows Forms 지역화](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)</span><span class="sxs-lookup"><span data-stu-id="3eade-179"> [Walkthrough: Localizing Windows Forms](http://msdn.microsoft.com/en-us/9a96220d-a19b-4de0-9f48-01e5d82679e5)</span></span>
