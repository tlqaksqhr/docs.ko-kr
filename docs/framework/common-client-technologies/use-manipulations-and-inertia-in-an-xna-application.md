---
title: "XNA 응용 프로그램에서 조작 및 관성 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
caps.latest.revision: "7"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7452a6001742bc9e0456ccb6339f13596a2ab72
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a><span data-ttu-id="88ca1-102">XNA 응용 프로그램에서 조작 및 관성 사용</span><span class="sxs-lookup"><span data-stu-id="88ca1-102">Using Manipulations and Inertia in an XNA Application</span></span>
<span data-ttu-id="88ca1-103">이 문서에서는 Microsoft XNA 응용 프로그램의 조작 및 관성 처리를 사용하여 게임 피스의 움직임을 제어하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="88ca1-103">This article describes how you can use manipulations and inertia processing in a Microsoft XNA application to control the movement of game pieces.</span></span> <span data-ttu-id="88ca1-104">이 문서를 읽기 전에 [조작 및 관성 개요](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) 항목 및 기본적인 XNA 프로그래밍 개념을 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ca1-104">Before you read this article, you should be familiar with the [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) topic, and be familiar with basic XNA programming concepts.</span></span>  
  
 <span data-ttu-id="88ca1-105">이 문서에 설명된 작업을 수행하려면 XNA 프로젝트가 <xref:System.Windows.Input.Manipulations> 어셈블리를 참조해야 하며, 프로젝트가 XNA 어셈블리를 참조할 수 있도록 [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx)([다운로드](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en))가 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ca1-105">To perform the tasks described in this article, your XNA project must reference the <xref:System.Windows.Input.Manipulations> assembly, and you must have [XNA Game Studio](http://msdn.microsoft.com/library/bb200104.aspx) ([download](http://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) installed on your computer so that your project can reference the XNA assemblies.</span></span>  
  
## <a name="overview-of-functionality"></a><span data-ttu-id="88ca1-106">기능 개요</span><span class="sxs-lookup"><span data-stu-id="88ca1-106">Overview of Functionality</span></span>  
 <span data-ttu-id="88ca1-107">이 문서에서는 조작 및 관성 처리를 사용하는 게임 피스를 나타내는 사용자 지정 클래스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="88ca1-107">This article shows you how to create a custom class that represents a game piece that uses manipulation and inertia processing.</span></span> <span data-ttu-id="88ca1-108">이 클래스를 통해 화면에서 게임 피스를 마우스로 끈 다음 놓아 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88ca1-108">This class enables you to manipulate a game piece across the screen by dragging it with the mouse, and then releasing it.</span></span> <span data-ttu-id="88ca1-109">놓고 나면 관성 처리에서 게임 피스가 점점 느려지면서 계속 움직이도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="88ca1-109">Once released, inertia processing keeps the game piece moving as it gradually slows down.</span></span> <span data-ttu-id="88ca1-110">움직임은 선형 및 각도 둘 다입니다.</span><span class="sxs-lookup"><span data-stu-id="88ca1-110">Movement is both linear and angular.</span></span>  
  
 <span data-ttu-id="88ca1-111">![간단한 조작 및 관성 응용 프로그램입니다.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span><span class="sxs-lookup"><span data-stu-id="88ca1-111">![A simple manipulations and inertia application.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span></span>  
  
 <span data-ttu-id="88ca1-112">또한 여러 게임 피스를 관리하는 사용자 지정 컬렉션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88ca1-112">In addition, a custom collection is created that manages multiple game pieces.</span></span> <span data-ttu-id="88ca1-113">그러면 XNA 게임 클래스에서 필요한 처리가 단순화됩니다.</span><span class="sxs-lookup"><span data-stu-id="88ca1-113">This simplifies the handling that is required from the XNA Game class.</span></span>  
  
 [<span data-ttu-id="88ca1-114">GamePiece 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="88ca1-114">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [<span data-ttu-id="88ca1-115">GamePieceCollection 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="88ca1-115">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [<span data-ttu-id="88ca1-116">Game1 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="88ca1-116">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [<span data-ttu-id="88ca1-117">전체 코드 목록</span><span class="sxs-lookup"><span data-stu-id="88ca1-117">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a><span data-ttu-id="88ca1-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88ca1-118">See Also</span></span>  
 <xref:System.Windows.Input.Manipulations>  
 [<span data-ttu-id="88ca1-119">조작 및 관성 개요</span><span class="sxs-lookup"><span data-stu-id="88ca1-119">Manipulations and Inertia Overview</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
