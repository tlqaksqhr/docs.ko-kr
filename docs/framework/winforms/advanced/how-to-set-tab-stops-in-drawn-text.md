---
title: '방법: 그린 텍스트에 탭 정지 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing with tab stops
- tabs [Windows Forms], drawn text
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
ms.openlocfilehash: e7f3fe9757db26bcc9dc9735f3d3d854edb7c099
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523639"
---
# <a name="how-to-set-tab-stops-in-drawn-text"></a><span data-ttu-id="9b780-102">방법: 그린 텍스트에 탭 정지 설정</span><span class="sxs-lookup"><span data-stu-id="9b780-102">How to: Set Tab Stops in Drawn Text</span></span>
<span data-ttu-id="9b780-103">호출 하 여 텍스트에 대 한 탭 정지를 설정할 수 있습니다는 <xref:System.Drawing.StringFormat.SetTabStops%2A> 메서드는 <xref:System.Drawing.StringFormat> 개체와 전달 하는 <xref:System.Drawing.StringFormat> 개체는 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스.</span><span class="sxs-lookup"><span data-stu-id="9b780-103">You can set tab stops for text by calling the <xref:System.Drawing.StringFormat.SetTabStops%2A> method of a <xref:System.Drawing.StringFormat> object and then passing that <xref:System.Drawing.StringFormat> object to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b780-104"><xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> 기존 탭을 확장할 수 있지만 그린된 텍스트에 탭 정지를 추가 하는 지원 하지 정지를 사용 하는 <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9b780-104">The <xref:System.Windows.Forms.TextRenderer?displayProperty=nameWithType> does not support adding tab stops to drawn text, although you can expand existing tab stops using the <xref:System.Windows.Forms.TextFormatFlags.ExpandTabs?displayProperty=nameWithType> flag.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b780-105">예제</span><span class="sxs-lookup"><span data-stu-id="9b780-105">Example</span></span>  
 <span data-ttu-id="9b780-106">다음 예제에서는 150, 250 및 350 탭 정지 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b780-106">The following example sets tab stops at 150, 250, and 350.</span></span> <span data-ttu-id="9b780-107">그런 다음 코드는 이름과 테스트 점수의 탭된 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b780-107">Then, the code displays a tabbed list of names and test scores.</span></span>  
  
 <span data-ttu-id="9b780-108">다음은 탭으로 이동한 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="9b780-108">The following illustration shows the tabbed text.</span></span>  
  
 <span data-ttu-id="9b780-109">![글꼴 텍스트](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span><span class="sxs-lookup"><span data-stu-id="9b780-109">![Fonts Text](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")</span></span>  
  
 <span data-ttu-id="9b780-110">다음 코드는 두 개의 인수를 전달 된 <xref:System.Drawing.StringFormat.SetTabStops%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9b780-110">The following code passes two arguments to the <xref:System.Drawing.StringFormat.SetTabStops%2A> method.</span></span> <span data-ttu-id="9b780-111">두 번째 인수가 탭 오프셋을 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9b780-111">The second argument is an array that contains tab offsets.</span></span> <span data-ttu-id="9b780-112">첫 번째 인수에 전달 된 <xref:System.Drawing.StringFormat.SetTabStops%2A> 은 0이 배열의 첫 번째 오프셋 위치 0는 경계 사각형의 왼쪽된 가장자리에서에서 측정 됩니다 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9b780-112">The first argument passed to <xref:System.Drawing.StringFormat.SetTabStops%2A> is 0, which indicates that the first offset in the array is measured from position 0, the left edge of the bounding rectangle.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b780-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9b780-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="9b780-114">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9b780-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b780-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b780-115">See Also</span></span>  
 [<span data-ttu-id="9b780-116">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="9b780-116">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [<span data-ttu-id="9b780-117">방법: GDI를 사용하여 텍스트 그리기</span><span class="sxs-lookup"><span data-stu-id="9b780-117">How to: Draw Text with GDI</span></span>](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
