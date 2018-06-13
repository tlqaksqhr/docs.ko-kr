---
title: '방법: 창'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 23dc74666d8f47a0fb735d96ad22ed56c96bdbc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545466"
---
# <a name="how-to-open-a-window"></a><span data-ttu-id="ac0e1-102">방법: 창</span><span class="sxs-lookup"><span data-stu-id="ac0e1-102">How to: Open a Window</span></span>
<span data-ttu-id="ac0e1-103">이 예제에는 창을 여는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac0e1-103">This example shows how to open a window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ac0e1-104">예제</span><span class="sxs-lookup"><span data-stu-id="ac0e1-104">Example</span></span>  
 <span data-ttu-id="ac0e1-105">인스턴스화하여 창이 열릴 <xref:System.Windows.Window> 호출는 <xref:System.Windows.Window.Show%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="ac0e1-105">A window is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="ac0e1-106"><xref:System.Windows.Window.Show%2A> 창을 열고 새 창이 닫힐 때까지 기다리지 않고 즉시 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac0e1-106"><xref:System.Windows.Window.Show%2A> opens a window and returns immediately without waiting for the new window to close.</span></span> <span data-ttu-id="ac0e1-107">이 창 유형에 라고도 *모덜리스* 창 하며 사용자 입력을 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac0e1-107">This type of window is also known as a *modeless* window, and doesn't restrict user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="ac0e1-108">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="ac0e1-108">.NET Framework Security</span></span>  
 <span data-ttu-id="ac0e1-109">인스턴스화 <xref:System.Windows.Window> 안전 하지 않은 네이티브 메서드를 호출 하기 위한 권한이 필요 (참조 <xref:System.Windows.Window.%23ctor%2A>).</span><span class="sxs-lookup"><span data-stu-id="ac0e1-109">Instantiating <xref:System.Windows.Window> requires permission to call unsafe native methods (see <xref:System.Windows.Window.%23ctor%2A>).</span></span>
