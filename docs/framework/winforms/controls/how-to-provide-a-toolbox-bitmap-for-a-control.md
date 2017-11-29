---
title: "방법: 컨트롤에 대한 도구 상자 비트맵 제공"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Toolbox [Windows Forms], adding bitmaps for custom controls
- custom controls [Windows Forms], Toolbox bitmaps
- bitmaps [Windows Forms], custom controls
ms.assetid: 0ed0840a-616d-41ba-a27d-3573241932ad
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d1ab49b6596c6feaa2ead5bbb92525f0ddb356d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-provide-a-toolbox-bitmap-for-a-control"></a><span data-ttu-id="96494-102">방법: 컨트롤에 대한 도구 상자 비트맵 제공</span><span class="sxs-lookup"><span data-stu-id="96494-102">How to: Provide a Toolbox Bitmap for a Control</span></span>
<span data-ttu-id="96494-103">컨트롤에 대 한 특수 아이콘에 표시 하려는 경우는 **도구 상자**를 사용 하 여 특정 이미지를 지정할 수 있습니다는 <xref:System.Drawing.ToolboxBitmapAttribute>합니다.</span><span class="sxs-lookup"><span data-stu-id="96494-103">If you want to have a special icon for your control appear in the **Toolbox**, you can specify a particular image by using the <xref:System.Drawing.ToolboxBitmapAttribute>.</span></span> <span data-ttu-id="96494-104">이 클래스는 *특성*이라는 다른 클래스에 연결할 수 있는 특수한 유형의 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="96494-104">This class is an *attribute*, a special kind of class you can attach to other classes.</span></span> <span data-ttu-id="96494-105">특성에 대한 자세한 내용은 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]의 [빌드에 없음: Visual Basic의 특성 개요](http://msdn.microsoft.com/en-us/0d0cff64-892d-4f57-83bd-bef388553d4f) 및 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 [특성](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96494-105">For more information about attributes, see [NOT IN BUILD: Attributes Overview in Visual Basic](http://msdn.microsoft.com/en-us/0d0cff64-892d-4f57-83bd-bef388553d4f) for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] and [Attributes](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205) for [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span></span>  
  
 <span data-ttu-id="96494-106">사용 하는 <xref:System.Drawing.ToolboxBitmapAttribute>, 16x16 픽셀 비트맵에 대 한 경로 파일 이름을 나타내는 문자열을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96494-106">Using the <xref:System.Drawing.ToolboxBitmapAttribute>, you can specify a string that indicates the path and file name for a 16 by 16 pixel bitmap.</span></span> <span data-ttu-id="96494-107">그런 다음 이 비트맵은 **도구 상자**에 추가될 때 컨트롤 옆에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96494-107">This bitmap then appears next to your control when added to the **Toolbox**.</span></span> <span data-ttu-id="96494-108">지정할 수 있습니다는 <xref:System.Type>, 해당 형식과 연결 된 비트맵 로드 되는 경우.</span><span class="sxs-lookup"><span data-stu-id="96494-108">You can also specify a <xref:System.Type>, in which case the bitmap associated with that type is loaded.</span></span> <span data-ttu-id="96494-109">둘 다 지정 하는 경우는 <xref:System.Type> 하 고 지정 된 형식에 포함 된 어셈블리에서 문자열 매개 변수로 지정 된 이름의 이미지 리소스에 대 한 문자열로 컨트롤 검색는 <xref:System.Type> 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="96494-109">If you specify both a <xref:System.Type> and a string, the control searches for an image resource with the name specified by the string parameter in the assembly containing the type specified by the <xref:System.Type> parameter.</span></span>  
  
### <a name="to-specify-a-toolbox-bitmap-for-your-control"></a><span data-ttu-id="96494-110">컨트롤의 도구 상자 비트맵을 지정하려면</span><span class="sxs-lookup"><span data-stu-id="96494-110">To specify a Toolbox bitmap for your control</span></span>  
  
1.  <span data-ttu-id="96494-111">추가 <xref:System.Drawing.ToolboxBitmapAttribute> 컨트롤의 클래스 선언에는 `Class` 에 대 한 키워드 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], 및에 대 한 클래스 선언 위에 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="96494-111">Add the <xref:System.Drawing.ToolboxBitmapAttribute> to the class declaration of your control before the `Class` keyword for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], and above the class declaration for [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)].</span></span>  
  
    ```vb  
    ' Specifies the bitmap associated with the Button type.  
    <ToolboxBitmap(GetType(Button))> Class MyControl1  
    ' Specifies a bitmap file.  
    End Class  
    <ToolboxBitmap("C:\Documents and Settings\Joe\MyPics\myImage.bmp")> _  
       Class MyControl2  
    End Class  
    ' Specifies a type that indicates the assembly to search, and the name   
    ' of an image resource to look for.  
    <ToolboxBitmap(GetType(MyControl), "MyControlBitmap")> Class MyControl  
    End Class  
    ```  
  
    ```csharp  
    // Specifies the bitmap associated with the Button type.  
    [ToolboxBitmap(typeof(Button))]  
    class MyControl1 : UserControl  
    {  
    }  
    // Specifies a bitmap file.  
    [ToolboxBitmap(@"C:\Documents and Settings\Joe\MyPics\myImage.bmp")]  
    class MyControl2 : UserControl  
    {  
    }  
    // Specifies a type that indicates the assembly to search, and the name   
    // of an image resource to look for.  
    [ToolboxBitmap(typeof(MyControl), "MyControlBitmap")]  
    class MyControl : UserControl  
    {  
    }  
    ```  
  
2.  <span data-ttu-id="96494-112">프로젝트를 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="96494-112">Rebuild the project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="96494-113">비트맵은 자동으로 생성된 컨트롤 및 구성 요소의 도구 상자에 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96494-113">The bitmap does not appear in the Toolbox for autogenerated controls and components.</span></span> <span data-ttu-id="96494-114">비트맵을 보려면 **도구 상자 항목 선택** 대화 상자를 사용하여 컨트롤을 다시 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="96494-114">To see the bitmap, reload the control by using the **Choose Toolbox Items** dialog box.</span></span> <span data-ttu-id="96494-115">자세한 내용은 [연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="96494-115">For more information, see [Walkthrough: Automatically Populating the Toolbox with Custom Components](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96494-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96494-116">See Also</span></span>  
 <xref:System.Drawing.ToolboxBitmapAttribute>  
 [<span data-ttu-id="96494-117">연습: 도구 상자에 자동으로 사용자 지정 구성 요소 채우기</span><span class="sxs-lookup"><span data-stu-id="96494-117">Walkthrough: Automatically Populating the Toolbox with Custom Components</span></span>](../../../../docs/framework/winforms/controls/walkthrough-automatically-populating-the-toolbox-with-custom-components.md)  
 [<span data-ttu-id="96494-118">디자인 타임에 Windows Forms 컨트롤 개발</span><span class="sxs-lookup"><span data-stu-id="96494-118">Developing Windows Forms Controls at Design Time</span></span>](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)  
 [<span data-ttu-id="96494-119">특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="96494-119">Attributes (Visual Basic)</span></span>](~/docs/visual-basic/language-reference/attributes.md)  
 [<span data-ttu-id="96494-120">특성</span><span class="sxs-lookup"><span data-stu-id="96494-120">Attributes</span></span>](http://msdn.microsoft.com/library/ae334cee-d96c-4243-a5e3-06dd7fcaf205)
