---
title: "GamePieceCollection 클래스 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e4b037ee-1201-4a55-b198-0d6532ed6f35
caps.latest.revision: "8"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: b8b53e5890aaebbad2f0a5f0e058182193b11622
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="creating-the-gamepiececollection-class"></a><span data-ttu-id="dee15-102">GamePieceCollection 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="dee15-102">Creating the GamePieceCollection Class</span></span>
<span data-ttu-id="dee15-103">**GamePieceCollection** 클래스는 제네릭 목록 클래스에서 파생되고 여러 **GamePiece** 개체를 더 쉽게 관리하도록 메서드를 도입합니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-103">The **GamePieceCollection** class derives from the generic List class, and introduces methods to more easily manage multiple **GamePiece** objects.</span></span>  
  
## <a name="creating-the-code"></a><span data-ttu-id="dee15-104">코드 만들기</span><span class="sxs-lookup"><span data-stu-id="dee15-104">Creating the Code</span></span>  
 <span data-ttu-id="dee15-105">**GamePieceCollection** 클래스의 생성자는 개인 멤버 *capturedIndex*를 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-105">The constructor of the **GamePieceCollection** class initializes the private member *capturedIndex*.</span></span> <span data-ttu-id="dee15-106">이 필드는 현재 마우스 캡처가 있는 게임 부분을 추적하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-106">This field is used to track which of the game pieces currently has the mouse capture.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_PrivateMembersAndConstructor](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_privatemembersandconstructor)]  
  
 <span data-ttu-id="dee15-107">**ProcessInertia** 및 **Draw** 메서드는 컬렉션에서 모든 게임 부분을 열거하고 각 **GamePiece** 개체에서 각 메서드를 호출하여 게임 [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) 및 [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) 메서드에 필요한 코드를 간소화합니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-107">The **ProcessInertia** and the **Draw** methods simplify the code needed in the game [Game.Update](http://msdn.microsoft.com/library/microsoft.xna.framework.game.update.aspx) and [Game.Draw](http://msdn.microsoft.com/library/microsoft.xna.framework.game.draw.aspx) methods by enumerating all of the game pieces in the collection and calling the respective method on each **GamePiece** object.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_ProcessInertiaAndDraw](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_processinertiaanddraw)]  
  
 <span data-ttu-id="dee15-108">게임 업데이트 중에 **UpdateFromMouse** 메서드도 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-108">The **UpdateFromMouse** method is also called during game update.</span></span> <span data-ttu-id="dee15-109">먼저 현재 캡처(있는 경우)가 계속 적용되는지 확인하여 마우스 캡처가 한 게임 부분에만 포함되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-109">It enables only one game piece to have the mouse capture by first checking to see if the current capture (if any) is still in effect.</span></span> <span data-ttu-id="dee15-110">그렇다면 다른 부분에 캡처가 있는지 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-110">If so, no other piece is allowed to check for capture.</span></span>  
  
 <span data-ttu-id="dee15-111">현재 캡처가 포함된 부분이 없으면 **UpdateFromMouse** 메서드가 마지막부터 처음까지 각 게임 부분을 열거하고 해당 부분에서 마우스 캡처를 보고하는지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-111">If no piece currently has the capture, the **UpdateFromMouse** method enumerates each game piece from last to first, and checks to see if that piece reports a mouse capture.</span></span> <span data-ttu-id="dee15-112">그렇다면 해당 부분은 현재 캡처된 부분이 되고 추가적인 처리가 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-112">If so, that piece becomes the current captured piece, and no further processing takes place.</span></span> <span data-ttu-id="dee15-113">**UpdateFromMouse** 메서드는 컬렉션의 마지막 항목을 먼저 확인하므로 두 부분이 겹치면 더 높은 Z 순서를 가진 한 부분이 캡처를 획득합니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-113">The **UpdateFromMouse** method checks the last item in the collection first so that if two pieces are overlapped, the one with the higher Z-order will obtain the capture.</span></span> <span data-ttu-id="dee15-114">Z 순서는 명시적이지 않고 변경할 수 없습니다. 단순히 게임 부분이 컬렉션에 추가된 순서대로 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="dee15-114">Z-order is not explicit nor changeable; it is governed simply by the order in which game pieces are added to the collection.</span></span>  
  
 [!code-csharp[ManipulationXNA#_GamePieceCollection_UpdateFromMouse](../../../samples/snippets/csharp/VS_Snippets_Misc/manipulationxna/cs/gamepiececollection.cs#_gamepiececollection_updatefrommouse)]  
  
## <a name="see-also"></a><span data-ttu-id="dee15-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dee15-115">See Also</span></span>  
 [<span data-ttu-id="dee15-116">조작 및 관성</span><span class="sxs-lookup"><span data-stu-id="dee15-116">Manipulations and Inertia</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia.md)  
 [<span data-ttu-id="dee15-117">XNA 응용 프로그램에서 조작 및 관성 사용</span><span class="sxs-lookup"><span data-stu-id="dee15-117">Using Manipulations and Inertia in an XNA Application</span></span>](../../../docs/framework/common-client-technologies/use-manipulations-and-inertia-in-an-xna-application.md)  
 [<span data-ttu-id="dee15-118">GamePiece 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="dee15-118">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
 [<span data-ttu-id="dee15-119">Game1 클래스 만들기</span><span class="sxs-lookup"><span data-stu-id="dee15-119">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
 [<span data-ttu-id="dee15-120">전체 코드 목록</span><span class="sxs-lookup"><span data-stu-id="dee15-120">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)
