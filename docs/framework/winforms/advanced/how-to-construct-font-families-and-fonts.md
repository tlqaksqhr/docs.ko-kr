---
title: "방법: 글꼴 패밀리 및 글꼴 만들기"
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
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e152c525550554082d7d6c38a972ccc150adabb9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="e5fdc-102">방법: 글꼴 패밀리 및 글꼴 만들기</span><span class="sxs-lookup"><span data-stu-id="e5fdc-102">How to: Construct Font Families and Fonts</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="e5fdc-103">글꼴 패밀리에 글꼴 서체 하지만 다양 한 스타일을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-103"> groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="e5fdc-104">예를 들어 Arial 글꼴 패밀리에는 다음 글꼴을 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-104">For example, the Arial font family contains the following fonts:</span></span>  
  
-   <span data-ttu-id="e5fdc-105">Arial 일반</span><span class="sxs-lookup"><span data-stu-id="e5fdc-105">Arial Regular</span></span>  
  
-   <span data-ttu-id="e5fdc-106">Arial 굵게 표시</span><span class="sxs-lookup"><span data-stu-id="e5fdc-106">Arial Bold</span></span>  
  
-   <span data-ttu-id="e5fdc-107">Arial 기울임꼴</span><span class="sxs-lookup"><span data-stu-id="e5fdc-107">Arial Italic</span></span>  
  
-   <span data-ttu-id="e5fdc-108">Arial Bold Italic</span><span class="sxs-lookup"><span data-stu-id="e5fdc-108">Arial Bold Italic</span></span>  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="e5fdc-109">패밀리를 구성 하기 위해 네 개의 스타일을 사용 하 여: 일반, 굵게, 기울임꼴 및 굵은 기울임꼴 등.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-109"> uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="e5fdc-110">형용사와 같은 *좁힐* 및 *반올림* 스타일; 간주 되지 않는 대신의 일부인 제품군 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="e5fdc-111">예, 굴림은 다음 멤버로 구성 된 글꼴 패밀리입니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
-   <span data-ttu-id="e5fdc-112">Arial 좁은 일반</span><span class="sxs-lookup"><span data-stu-id="e5fdc-112">Arial Narrow Regular</span></span>  
  
-   <span data-ttu-id="e5fdc-113">굵게 표시 된 arial 좁은</span><span class="sxs-lookup"><span data-stu-id="e5fdc-113">Arial Narrow Bold</span></span>  
  
-   <span data-ttu-id="e5fdc-114">Arial 좁은 기울임꼴</span><span class="sxs-lookup"><span data-stu-id="e5fdc-114">Arial Narrow Italic</span></span>  
  
-   <span data-ttu-id="e5fdc-115">Arial 좁은 Bold Italic</span><span class="sxs-lookup"><span data-stu-id="e5fdc-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="e5fdc-116">텍스트를 그릴 수 전에 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]를 생성 해야는 <xref:System.Drawing.FontFamily> 개체 및 <xref:System.Drawing.Font> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-116">Before you can draw text with [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="e5fdc-117"><xref:System.Drawing.FontFamily> 개체 지정 (예: Arial) 서체 및 <xref:System.Drawing.Font> 개체 크기, 스타일 및 단위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5fdc-118">예</span><span class="sxs-lookup"><span data-stu-id="e5fdc-118">Example</span></span>  
 <span data-ttu-id="e5fdc-119">다음 예제에서는 일반 스타일 Arial 글꼴 크기는 16 픽셀을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="e5fdc-120">다음 코드에서에 전달 되는 첫 번째 인수는 <xref:System.Drawing.Font.%23ctor%2A> 생성자는는 <xref:System.Drawing.FontFamily> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="e5fdc-121">두 번째 인수는 네 번째 인수에 의해 식별 된 단위로 측정 되는 글꼴의 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="e5fdc-122">세 번째 인수는 스타일을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="e5fdc-123"><xref:System.Drawing.GraphicsUnit.Pixel>멤버인는 <xref:System.Drawing.GraphicsUnit> 열거형 및 <xref:System.Drawing.FontStyle.Regular> 의 구성원은 <xref:System.Drawing.FontStyle> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e5fdc-124">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e5fdc-124">Compiling the Code</span></span>  
 <span data-ttu-id="e5fdc-125">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventArgs>의 매개 변수인 `e`<xref:System.Windows.Forms.PaintEventHandler>가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e5fdc-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs>`e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5fdc-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5fdc-126">See Also</span></span>  
 [<span data-ttu-id="e5fdc-127">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="e5fdc-127">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="e5fdc-128">Windows Forms의 그래픽 및 그리기</span><span class="sxs-lookup"><span data-stu-id="e5fdc-128">Graphics and Drawing in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
