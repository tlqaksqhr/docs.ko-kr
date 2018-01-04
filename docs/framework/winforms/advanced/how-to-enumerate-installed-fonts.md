---
title: "방법: 설치된 글꼴 열거"
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
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 905b5ecbda58d2f7edb7fc30d5505eec63a64c2b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="ee19c-102">방법: 설치된 글꼴 열거</span><span class="sxs-lookup"><span data-stu-id="ee19c-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="ee19c-103"><xref:System.Drawing.Text.InstalledFontCollection> 클래스에서 상속 된 <xref:System.Drawing.Text.FontCollection> 추상 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ee19c-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="ee19c-104">사용할 수는 <xref:System.Drawing.Text.InstalledFontCollection> 컴퓨터에 설치 된 글꼴 열거 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ee19c-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="ee19c-105"><xref:System.Drawing.Text.FontCollection.Families%2A> 속성은 <xref:System.Drawing.Text.InstalledFontCollection> 개체의 배열이 <xref:System.Drawing.FontFamily> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ee19c-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee19c-106">예</span><span class="sxs-lookup"><span data-stu-id="ee19c-106">Example</span></span>  
 <span data-ttu-id="ee19c-107">다음 예제에는 컴퓨터에 설치 된 모든 글꼴 패밀리의 이름을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee19c-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="ee19c-108">코드 검색은 <xref:System.Drawing.FontFamily.Name%2A> 각 속성 <xref:System.Drawing.FontFamily> 에서 반환 된 배열에 있는 개체는 <xref:System.Drawing.Text.FontCollection.Families%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="ee19c-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="ee19c-109">패밀리 이름을 검색 하는 쉼표로 구분 된 형식 목록에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee19c-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="ee19c-110">그런 다음 <xref:System.Drawing.Graphics.DrawString%2A> 의 메서드는 <xref:System.Drawing.Graphics> 클래스 사각형에 쉼표로 구분 된 목록을 그립니다.</span><span class="sxs-lookup"><span data-stu-id="ee19c-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="ee19c-111">예제 코드를 실행 하는 경우 출력 다음 그림에 표시 된 것과 비슷한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ee19c-111">If you run the example code, the output will be similar to that shown in the following illustration.</span></span>  
  
 <span data-ttu-id="ee19c-112">![설치 된 글꼴](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span><span class="sxs-lookup"><span data-stu-id="ee19c-112">![Installed Fonts](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ee19c-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="ee19c-113">Compiling the Code</span></span>  
 <span data-ttu-id="ee19c-114">앞의 예제는 Windows forms에서 사용하도록 설계되었으며 <xref:System.Windows.Forms.PaintEventHandler>의 매개 변수인 <xref:System.Windows.Forms.PaintEventArgs> `e`가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ee19c-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="ee19c-115">또한 가져오는 것이 고 <xref:System.Drawing.Text> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ee19c-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee19c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee19c-116">See Also</span></span>  
 [<span data-ttu-id="ee19c-117">글꼴 및 텍스트 사용</span><span class="sxs-lookup"><span data-stu-id="ee19c-117">Using Fonts and Text</span></span>](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
