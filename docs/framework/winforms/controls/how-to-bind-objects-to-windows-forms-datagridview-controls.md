---
title: '방법: Windows Forms DataGridView 컨트롤에 개체 바인딩'
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
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d8cb84608c0aeead00e56d2d91489954e4b7fca6
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="fbd78-102">방법: Windows Forms DataGridView 컨트롤에 개체 바인딩</span><span class="sxs-lookup"><span data-stu-id="fbd78-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="fbd78-103">다음 코드 예제에서는 각 개체가 개별 행으로 표시되도록 개체 컬렉션을 <xref:System.Windows.Forms.DataGridView> 컨트롤에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fbd78-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="fbd78-104">이 예제에서는 콤보 상자 드롭다운 목록에 열거형 값이 포함되도록 <xref:System.Windows.Forms.DataGridViewComboBoxColumn>에서 열거형 형식을 가진 속성을 표시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fbd78-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbd78-105">예제</span><span class="sxs-lookup"><span data-stu-id="fbd78-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fbd78-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fbd78-106">Compiling the Code</span></span>  
 <span data-ttu-id="fbd78-107">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd78-107">This example requires:</span></span>  
  
-   <span data-ttu-id="fbd78-108">System 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="fbd78-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="fbd78-109">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fbd78-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fbd78-110">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbd78-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="fbd78-111">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbd78-111">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd78-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbd78-112">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="fbd78-113">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="fbd78-113">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="fbd78-114">방법: Windows Forms DataGridView 행에 바인딩된 개체에 액세스</span><span class="sxs-lookup"><span data-stu-id="fbd78-114">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](../../../../docs/framework/winforms/controls/how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
