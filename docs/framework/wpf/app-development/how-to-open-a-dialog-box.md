---
title: "방법: 대화 상자 열기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d318f35f8f009f0f2c77210ca8b6b29bedfb7619
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-open-a-dialog-box"></a><span data-ttu-id="a21d8-102">방법: 대화 상자 열기</span><span class="sxs-lookup"><span data-stu-id="a21d8-102">How to: Open a Dialog Box</span></span>
<span data-ttu-id="a21d8-103">이 예제에는 대화 상자를 여는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a21d8-103">This example shows how to open a dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a21d8-104">예제</span><span class="sxs-lookup"><span data-stu-id="a21d8-104">Example</span></span>  
 <span data-ttu-id="a21d8-105">대화 상자는 인스턴스화하여 열려 있는 창을 <xref:System.Windows.Window> 호출는 <xref:System.Windows.Window.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a21d8-105">A dialog box is a window that is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.ShowDialog%2A> method.</span></span> <span data-ttu-id="a21d8-106"><xref:System.Windows.Window.ShowDialog%2A>창을 열고 새 대화 상자가 닫힐 때까지 반환 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a21d8-106"><xref:System.Windows.Window.ShowDialog%2A> opens a window and doesn't return until the new dialog box has been closed.</span></span> <span data-ttu-id="a21d8-107">이러한 형식의 라고도 *모달* 창 및 사용자 입력을 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a21d8-107">This type of window is also known as a *modal* window, and restricts user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="a21d8-108">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="a21d8-108">.NET Framework Security</span></span>  
 <span data-ttu-id="a21d8-109">호출 <xref:System.Windows.Window.ShowDialog%2A> 모든 창과 사용자 입력된 이벤트를 제한 없이 사용할 수 있는 권한이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a21d8-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a21d8-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a21d8-110">See Also</span></span>  
 [<span data-ttu-id="a21d8-111">대화 상자 결과 반환</span><span class="sxs-lookup"><span data-stu-id="a21d8-111">Return a Dialog Box Result</span></span>](../../../../docs/framework/wpf/app-development/how-to-return-a-dialog-box-result.md)
