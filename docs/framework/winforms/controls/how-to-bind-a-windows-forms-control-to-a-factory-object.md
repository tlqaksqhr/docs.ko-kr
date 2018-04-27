---
title: '방법: 팩터리 개체에 Windows Forms 컨트롤 바인딩'
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
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0c489227d12afd5e6d63a43c752ea97f06aa974e
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a><span data-ttu-id="13d68-102">방법: 팩터리 개체에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="13d68-102">How to: Bind a Windows Forms Control to a Factory Object</span></span>
<span data-ttu-id="13d68-103">데이터와 상호 작용하는 컨트롤을 빌드하는 경우 때로는 다른 개체를 생성하는 개체나 메서드에 컨트롤을 바인딩할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d68-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to an object or method that generates other objects.</span></span> <span data-ttu-id="13d68-104">이러한 개체나 메서드를 팩터리라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="13d68-104">Such an object or method is called a factory.</span></span> <span data-ttu-id="13d68-105">예를 들어 데이터 소스는 메모리 또는 형식의 개체가 아니라 메서드 호출의 반환 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d68-105">Your data source might be, for example, the return value from a method call, instead of an object in memory or a type.</span></span> <span data-ttu-id="13d68-106">소스가 컬렉션을 반환하는 한 컨트롤을 이러한 종류의 데이터 소스에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d68-106">You can bind a control to this kind of data source as long as the source returns a collection.</span></span>  
  
 <span data-ttu-id="13d68-107"><xref:System.Windows.Forms.BindingSource> 컨트롤을 사용하여 컨트롤을 팩터리 개체에 쉽게 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d68-107">You can easily bind a control to a factory object by using the <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13d68-108">예제</span><span class="sxs-lookup"><span data-stu-id="13d68-108">Example</span></span>  
 <span data-ttu-id="13d68-109">다음 예제에서는 <xref:System.Windows.Forms.BindingSource> 컨트롤을 사용하여 <xref:System.Windows.Forms.DataGridView> 컨트롤을 팩터리 메서드에 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="13d68-109">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a factory method by using a <xref:System.Windows.Forms.BindingSource> control.</span></span> <span data-ttu-id="13d68-110">팩터리 메서드는 이름이 `GetOrdersByCustomerId`이며, Northwind 데이터베이스에서 지정된 고객에 대한 모든 주문을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="13d68-110">The factory method is named `GetOrdersByCustomerId`, and it returns all the orders for a given customer in the Northwind database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="13d68-111">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="13d68-111">Compiling the Code</span></span>  
 <span data-ttu-id="13d68-112">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="13d68-112">This example requires:</span></span>  
  
-   <span data-ttu-id="13d68-113">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="13d68-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="13d68-114">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 정보를 참조 하십시오. [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [사용한 명령줄 빌드 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="13d68-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="13d68-115">새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13d68-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="13d68-116">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13d68-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d68-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13d68-117">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="13d68-118">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="13d68-118">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="13d68-119">방법: 형식에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="13d68-119">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
