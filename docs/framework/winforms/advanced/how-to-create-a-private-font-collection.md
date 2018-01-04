---
title: "방법: 개인 글꼴 컬렉션 만들기"
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
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8c0107b1ef1d5259835c6fb1666519d3fc06f4e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-private-font-collection"></a><span data-ttu-id="83353-102">방법: 개인 글꼴 컬렉션 만들기</span><span class="sxs-lookup"><span data-stu-id="83353-102">How to: Create a Private Font Collection</span></span>
<span data-ttu-id="83353-103"><xref:System.Drawing.Text.PrivateFontCollection> 클래스에서 상속 된 <xref:System.Drawing.Text.FontCollection> 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="83353-103">The <xref:System.Drawing.Text.PrivateFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="83353-104">사용할 수는 <xref:System.Drawing.Text.PrivateFontCollection> 응용 프로그램에 맞게 글꼴 집합을 유지 관리 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="83353-104">You can use a <xref:System.Drawing.Text.PrivateFontCollection> object to maintain a set of fonts specifically for your application.</span></span> <span data-ttu-id="83353-105">개인 글꼴 컬렉션으로 설치 된 시스템 글꼴 컴퓨터에 설치 되지 않은 글꼴을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83353-105">A private font collection can include installed system fonts as well as fonts that have not been installed on the computer.</span></span> <span data-ttu-id="83353-106">글꼴 파일을 개인 글꼴 컬렉션을 추가 하려면 호출는 <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> 의 메서드는 <xref:System.Drawing.Text.PrivateFontCollection> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="83353-106">To add a font file to a private font collection, call the <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> method of a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="83353-107"><xref:System.Drawing.Text.FontCollection.Families%2A> 속성은 <xref:System.Drawing.Text.PrivateFontCollection> 개체의 배열을 포함 <xref:System.Drawing.FontFamily> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="83353-107">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of a <xref:System.Drawing.Text.PrivateFontCollection> object contains an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
 <span data-ttu-id="83353-108">개인 글꼴 컬렉션에서 글꼴 패밀리 수가 않습니다 반드시 컬렉션에 추가 된 글꼴 파일의 개수와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="83353-108">The number of font families in a private font collection is not necessarily the same as the number of font files that have been added to the collection.</span></span> <span data-ttu-id="83353-109">예를 들어 ArialBd.tff, Times.tff, TimesBd.tff 파일 컬렉션에 추가 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="83353-109">For example, suppose you add the files ArialBd.tff, Times.tff, and TimesBd.tff to a collection.</span></span> <span data-ttu-id="83353-110">됩니다 3 개의 파일 하지만 컬렉션에 있는 두 패밀리 Times.tff 및 TimesBd.tff 동일한 제품군에 속하므로.</span><span class="sxs-lookup"><span data-stu-id="83353-110">There will be three files but only two families in the collection because Times.tff and TimesBd.tff belong to the same family.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83353-111">예</span><span class="sxs-lookup"><span data-stu-id="83353-111">Example</span></span>  
 <span data-ttu-id="83353-112">다음 예제에서는 다음 세 개의 글꼴 파일을 추가 하는 <xref:System.Drawing.Text.PrivateFontCollection> 개체:</span><span class="sxs-lookup"><span data-stu-id="83353-112">The following example adds the following three font files to a <xref:System.Drawing.Text.PrivateFontCollection> object:</span></span>  
  
-   <span data-ttu-id="83353-113">C:\\*systemroot*\Fonts\Arial.tff (굴림, 일반)</span><span class="sxs-lookup"><span data-stu-id="83353-113">C:\\*systemroot*\Fonts\Arial.tff (Arial, regular)</span></span>  
  
-   <span data-ttu-id="83353-114">C:\\*systemroot*\Fonts\CourBI.tff (분수에 굵은 기울임꼴)</span><span class="sxs-lookup"><span data-stu-id="83353-114">C:\\*systemroot*\Fonts\CourBI.tff (Courier New, bold italic)</span></span>  
  
-   <span data-ttu-id="83353-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman 굵게 표시)</span><span class="sxs-lookup"><span data-stu-id="83353-115">C:\\*systemroot*\Fonts\TimesBd.tff (Times New Roman, bold)</span></span>  
  
 <span data-ttu-id="83353-116">코드의 검색 <xref:System.Drawing.FontFamily> 에서 개체는 <xref:System.Drawing.Text.FontCollection.Families%2A> 속성은 <xref:System.Drawing.Text.PrivateFontCollection> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="83353-116">The code retrieves an array of <xref:System.Drawing.FontFamily> objects from the <xref:System.Drawing.Text.FontCollection.Families%2A> property of the <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 <span data-ttu-id="83353-117">각 <xref:System.Drawing.FontFamily> 코드를 호출 하 여 컬렉션의 개체는 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> (일반, 굵게, 기울임꼴, 기울임꼴 굵게, 밑줄 및 취소선) 다양 한 스타일을 사용할 수 있는지 여부를 결정 하는 메서드.</span><span class="sxs-lookup"><span data-stu-id="83353-117">For each <xref:System.Drawing.FontFamily> object in the collection, the code calls the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method to determine whether various styles (regular, bold, italic, bold italic, underline, and strikeout) are available.</span></span> <span data-ttu-id="83353-118">인수 전달 되는 <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> 의 멤버인 메서드는 <xref:System.Drawing.FontStyle> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="83353-118">The arguments passed to the <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> method are members of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 <span data-ttu-id="83353-119">지정 된 제품군/스타일 조합을 사용할 수 있는 경우는 <xref:System.Drawing.Font> 해당 제품군 및 스타일을 사용 하 여 개체가 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="83353-119">If a given family/style combination is available, a <xref:System.Drawing.Font> object is constructed using that family and style.</span></span> <span data-ttu-id="83353-120">에 전달 되는 첫 번째 인수는 <xref:System.Drawing.Font.%23ctor%2A> 생성자는 글꼴 패밀리 이름 (하지는 <xref:System.Drawing.FontFamily> 다른 변형에 대 한 경우와 마찬가지로 개체는 <xref:System.Drawing.Font.%23ctor%2A> 생성자).</span><span class="sxs-lookup"><span data-stu-id="83353-120">The first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the font family name (not a <xref:System.Drawing.FontFamily> object as is the case for other variations of the <xref:System.Drawing.Font.%23ctor%2A> constructor).</span></span> <span data-ttu-id="83353-121">후의 <xref:System.Drawing.Font> 개체가 만들어지면에 전달 되는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 스타일의 이름과 함께 제품군 이름을 표시 하는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="83353-121">After the <xref:System.Drawing.Font> object is constructed, it is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class to display the family name along with the name of the style.</span></span>  
  
 <span data-ttu-id="83353-122">다음 코드의 출력은 다음 그림에 표시 된 출력과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="83353-122">The output of the following code is similar to the output shown in the following illustration.</span></span>  
  
 <span data-ttu-id="83353-123">![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")</span><span class="sxs-lookup"><span data-stu-id="83353-123">![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext7.png "csfontstext7")</span></span>  
  
 <span data-ttu-id="83353-124">(다음 코드 예제에 개인 글꼴 컬렉션에 추가 된) 함 Arial.tff는 Arial 보통 스타일에 대 한 글꼴 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="83353-124">Arial.tff (which was added to the private font collection in the following code example) is the font file for the Arial regular style.</span></span> <span data-ttu-id="83353-125">단, 사용할 수 있는 스타일이 Arial 글꼴 패밀리에 대 한 보통 외에 몇 가지 프로그램 출력에 표시 되는지 합니다.</span><span class="sxs-lookup"><span data-stu-id="83353-125">Note, however, that the program output shows several available styles other than regular for the Arial font family.</span></span> <span data-ttu-id="83353-126">때문 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 굵게, 기울임꼴 및 b o l 기울임꼴 스타일 보통 스타일을 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83353-126">That is because [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold, italic, and bold italic styles from the regular style.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="83353-127">일반 스타일의 밑줄과 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83353-127"> can also produce underlines and strikeouts from the regular style.</span></span>  
  
 <span data-ttu-id="83353-128">마찬가지로, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 굵은 기울임꼴 스타일은 굵게 또는 기울임꼴 스타일을 시뮬레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83353-128">Similarly, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] can simulate the bold italic style from either the bold style or the italic style.</span></span> <span data-ttu-id="83353-129">프로그램 출력 TimesBd.tff (Times New Roman 굵게 표시)는 유일 하 게 하는 경우에 굵은 기울임꼴 스타일의 시간 제품군에 사용할 수 있는 임을 보여주고 컬렉션에 파일 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="83353-129">The program output shows that the bold italic style is available for the Times family even though TimesBd.tff (Times New Roman, bold) is the only Times file in the collection.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#51](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="83353-130">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="83353-130">Compiling the Code</span></span>  
 <span data-ttu-id="83353-131">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83353-131">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83353-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83353-132">See Also</span></span>  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 [<span data-ttu-id="83353-133">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="83353-133">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
