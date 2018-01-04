---
title: "방법: DBNull 데이터베이스 값에 Windows Forms 컨트롤 바인딩"
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
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c96fd6d09b2ddefce4c682976fcff86c9b562a3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a><span data-ttu-id="a51ae-102">방법: DBNull 데이터베이스 값에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="a51ae-102">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>
<span data-ttu-id="a51ae-103">Windows Forms 컨트롤을 데이터 소스에 바인딩하고 데이터 소스가 <xref:System.DBNull> 값을 반환하는 경우 이벤트를 처리, 형식 지정 또는 구문 분석하지 않고 적절한 값을 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a51ae-103">When you bind Windows Forms controls to a data source and the data source returns a <xref:System.DBNull> value, you can substitute an appropriate value without handling, formatting, or parsing events.</span></span> <span data-ttu-id="a51ae-104"><xref:System.Windows.Forms.Binding.NullValue%2A> 속성은 데이터 소스 값을 형식 지정 또는 구문 분석할 때 <xref:System.DBNull>을 지정된 개체로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="a51ae-104">The <xref:System.Windows.Forms.Binding.NullValue%2A> property will convert <xref:System.DBNull> to a specified object when formatting or parsing the data source values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a51ae-105">예</span><span class="sxs-lookup"><span data-stu-id="a51ae-105">Example</span></span>  
 <span data-ttu-id="a51ae-106">다음 예제에서는 두 가지 다른 상황에서 <xref:System.DBNull> 값을 바인딩하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a51ae-106">The following example demonstrates how to bind a <xref:System.DBNull> value in two different situations.</span></span> <span data-ttu-id="a51ae-107">첫 번째 예제에서는 문자열 속성에 대해 <xref:System.Windows.Forms.Binding.NullValue%2A>를 설정하는 방법을 보여 주고, 두 번째 예제에서는 이미지 속성에 대해 <xref:System.Windows.Forms.Binding.NullValue%2A>를 설정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a51ae-107">The first demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for a string property; the second demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for an image property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 <span data-ttu-id="a51ae-108">바인딩된 속성의 형식 및 <xref:System.Windows.Forms.Binding.NullValue%2A> 속성은 같아야 합니다. 그러지 않으면 오류가 발생하고 더 이상 <xref:System.Windows.Forms.Binding.NullValue%2A> 값이 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a51ae-108">The types of the bound property and the <xref:System.Windows.Forms.Binding.NullValue%2A> property must be the same or an error will result, and no further <xref:System.Windows.Forms.Binding.NullValue%2A> values will be processed.</span></span> <span data-ttu-id="a51ae-109">이 경우 예외가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a51ae-109">In this situation, an exception will not be thrown.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a51ae-110">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="a51ae-110">Compiling the Code</span></span>  
 <span data-ttu-id="a51ae-111">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a51ae-111">This example requires:</span></span>  
  
-   <span data-ttu-id="a51ae-112">System, System.Data, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="a51ae-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="a51ae-113">[!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 또는 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]의 명령줄에서 이 예제를 빌드하는 방법에 대한 자세한 내용은 [명령줄에서 빌드](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 또는 [csc.exe를 사용한 명령줄 빌드](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a51ae-113">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="a51ae-114">[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]에서 코드를 새 프로젝트에 붙여넣어 이 예제를 빌드할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a51ae-114">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="a51ae-115">[방법: Visual Studio를 사용하여 전체 Windows Forms 코드 예제 컴파일 및 실행](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a51ae-115">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a51ae-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a51ae-116">See Also</span></span>  
 [<span data-ttu-id="a51ae-117">BindingSource 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a51ae-117">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="a51ae-118">방법: 데이터 바인딩에서 발생하는 오류 및 예외 처리</span><span class="sxs-lookup"><span data-stu-id="a51ae-118">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 [<span data-ttu-id="a51ae-119">방법: 형식에 Windows Forms 컨트롤 바인딩</span><span class="sxs-lookup"><span data-stu-id="a51ae-119">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
