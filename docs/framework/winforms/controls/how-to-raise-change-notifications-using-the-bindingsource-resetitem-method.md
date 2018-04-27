---
title: '방법: BindingSource ResetItem 메서드를 사용하여 변경 알림 발생'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 911e96ee58660b428186e749113dafbcc2037d97
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a><span data-ttu-id="e8077-102">방법: BindingSource ResetItem 메서드를 사용하여 변경 알림 발생</span><span class="sxs-lookup"><span data-stu-id="e8077-102">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>
<span data-ttu-id="e8077-103">컨트롤에 대한 일부 데이터 소스는 항목이 변경, 추가 또는 삭제될 때 변경 알림을 발생시키지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8077-103">Some data sources for your controls do not raise change notifications when items are changed, added, or deleted.</span></span> <span data-ttu-id="e8077-104"><xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 이러한 데이터 소스에 바인딩하고 코드에서 변경 알림을 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8077-104">With the <xref:System.Windows.Forms.BindingSource> component, you can bind to such data sources and raise a change notification from your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e8077-105">예제</span><span class="sxs-lookup"><span data-stu-id="e8077-105">Example</span></span>  
 <span data-ttu-id="e8077-106">이 폼은 <xref:System.Windows.Forms.BindingSource> 구성 요소를 사용하여 목록을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8077-106">This form demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind a list to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="e8077-107">목록에서 변경 알림이 발생하지 않으므로 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.ResetItem%2A> 메서드는 목록의 항목이 변경될 때 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8077-107">The list does not raise change notifications, so the <xref:System.Windows.Forms.BindingSource.ResetItem%2A> method on the <xref:System.Windows.Forms.BindingSource> is called when an item in the list is changed.</span></span> <span data-ttu-id="e8077-108">이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8077-108">.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e8077-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="e8077-109">Compiling the Code</span></span>  
 <span data-ttu-id="e8077-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e8077-110">This example requires:</span></span>  
  
-   <span data-ttu-id="e8077-111">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="e8077-111">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="e8077-112">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e8077-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e8077-113">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8077-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="e8077-114">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e8077-114">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8077-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8077-115">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="e8077-116">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="e8077-116">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="e8077-117">방법: 형식에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="e8077-117">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
