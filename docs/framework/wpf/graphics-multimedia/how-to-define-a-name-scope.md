---
title: '방법: 이름 범위 정의'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- name scope [WPF], defining
- Storyboards [WPF], animating in procedural code
- animation [WPF], Storyboards [WPF], in procedural code
ms.assetid: 4f361925-6a08-40dc-8231-a61111c6b28b
ms.openlocfilehash: 689c8187fcf17ef48a73bc5a6fc4928f3be1a078
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33559717"
---
# <a name="how-to-define-a-name-scope"></a><span data-ttu-id="0d84b-102">방법: 이름 범위 정의</span><span class="sxs-lookup"><span data-stu-id="0d84b-102">How to: Define a Name Scope</span></span>
<span data-ttu-id="0d84b-103">로 애니메이션 효과를 <xref:System.Windows.Media.Animation.Storyboard> 코드를 만들어야 합니다는 <xref:System.Windows.NameScope> 하 고 해당 이름 범위를 소유 하는 요소는 대상 개체의 이름을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d84b-103">To animate with <xref:System.Windows.Media.Animation.Storyboard> in code, you must create a <xref:System.Windows.NameScope> and register the target objects' names with the element that owns that name scope.</span></span> <span data-ttu-id="0d84b-104">다음 예제에서는 <xref:System.Windows.NameScope> 만들어집니다 `myMainPanel`합니다.</span><span class="sxs-lookup"><span data-stu-id="0d84b-104">In the following example, a <xref:System.Windows.NameScope> is created for `myMainPanel`.</span></span> <span data-ttu-id="0d84b-105">두 개의 단추 `button1` 및 `button2`, 패널과 이름을 등록에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d84b-105">Two buttons, `button1` and `button2`, are added to the panel, and their names registered.</span></span> <span data-ttu-id="0d84b-106">여러 개의 애니메이션 및 <xref:System.Windows.Media.Animation.Storyboard> 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="0d84b-106">Several animations and a <xref:System.Windows.Media.Animation.Storyboard> are created.</span></span> <span data-ttu-id="0d84b-107">스토리 보드의 <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드는 애니메이션을 시작 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d84b-107">The storyboard's <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method is used to start the animations.</span></span>  
  
 <span data-ttu-id="0d84b-108">때문에 `button1`, `button2`, 및 `myMainPanel` 동일한 이름 범위를 공유 하는 모든, 그 중 하나를 사용할 수 있습니다는 <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> 메서드를 애니메이션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0d84b-108">Because `button1`, `button2`, and `myMainPanel` all share the same name scope, any one of them can be used with the <xref:System.Windows.Media.Animation.Storyboard> <xref:System.Windows.Media.Animation.Storyboard.Begin%2A> method to start the animations.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d84b-109">예제</span><span class="sxs-lookup"><span data-stu-id="0d84b-109">Example</span></span>  
 [!code-csharp[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/CSharp/ScopeExample.cs#namescopeexample)]
 [!code-vb[StoryboardBeginAnimation_procedural_snip#NameScopeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StoryboardBeginAnimation_procedural_snip/visualbasic/scopeexample.vb#namescopeexample)]  
  
## <a name="see-also"></a><span data-ttu-id="0d84b-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d84b-110">See Also</span></span>  
 [<span data-ttu-id="0d84b-111">Storyboard를 사용하여 속성에 애니메이션 효과 주기</span><span class="sxs-lookup"><span data-stu-id="0d84b-111">Animate a Property by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-by-using-a-storyboard.md)  
 [<span data-ttu-id="0d84b-112">애니메이션 개요</span><span class="sxs-lookup"><span data-stu-id="0d84b-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
