---
title: "방법: PropertyNameChanged 패턴 적용"
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
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1afe397a92ac6e79e84757baa0c41f6e0c54b7f2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="dcf1f-102">방법: PropertyNameChanged 패턴 적용</span><span class="sxs-lookup"><span data-stu-id="dcf1f-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="dcf1f-103">다음 코드 예제에서는 적용 하는 방법을 보여 줍니다.는 *PropertyName*패턴을 사용자 지정 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="dcf1f-104">Windows Forms 데이터 바인딩 엔진에 사용 되는 사용자 지정 컨트롤을 구현 하는 경우이 패턴을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dcf1f-105">예</span><span class="sxs-lookup"><span data-stu-id="dcf1f-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dcf1f-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="dcf1f-106">Compiling the Code</span></span>  
 <span data-ttu-id="dcf1f-107">이전 코드 예제를 컴파일하려면:</span><span class="sxs-lookup"><span data-stu-id="dcf1f-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="dcf1f-108">빈 코드 파일에 코드를 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="dcf1f-109">포함 된 Windows Form에 사용자 지정 컨트롤을 사용 해야는 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="dcf1f-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dcf1f-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcf1f-110">See Also</span></span>  
 [<span data-ttu-id="dcf1f-111">방법: INotifyPropertyChanged 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="dcf1f-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 [<span data-ttu-id="dcf1f-112">Windows Forms 데이터 바인딩의 변경 알림</span><span class="sxs-lookup"><span data-stu-id="dcf1f-112">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="dcf1f-113">Windows Forms 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="dcf1f-113">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
