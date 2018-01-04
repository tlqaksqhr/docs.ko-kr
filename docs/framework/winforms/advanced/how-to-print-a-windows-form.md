---
title: "방법: Windows Form 인쇄"
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
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8c50b1f47d207334160ed12674ee8efb1390fb84
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="fa10f-102">방법: Windows Form 인쇄</span><span class="sxs-lookup"><span data-stu-id="fa10f-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="fa10f-103">개발 프로세스의 일환으로, 일반적으로 할 Windows Form의 복사본을 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa10f-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="fa10f-104">다음 코드 예제를 사용 하 여 현재 폼의 복사본을 인쇄 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="fa10f-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa10f-105">예</span><span class="sxs-lookup"><span data-stu-id="fa10f-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fa10f-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="fa10f-106">Compiling the Code</span></span>  
 <span data-ttu-id="fa10f-107">이 포함 하는 전체 코드 예제는 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="fa10f-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="fa10f-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="fa10f-108">Robust Programming</span></span>  
 <span data-ttu-id="fa10f-109">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="fa10f-109">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="fa10f-110">프린터에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa10f-110">You do not have permission to access the printer.</span></span>  
  
-   <span data-ttu-id="fa10f-111">프린터가 설치 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fa10f-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="fa10f-112">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="fa10f-112">.NET Framework Security</span></span>  
 <span data-ttu-id="fa10f-113">이 코드 예제를 실행 하는 데 사용할 프린터를 사용 하 여 컴퓨터를 액세스할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa10f-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa10f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fa10f-114">See Also</span></span>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [<span data-ttu-id="fa10f-115">방법: GDI+를 사용하여 이미지 렌더링</span><span class="sxs-lookup"><span data-stu-id="fa10f-115">How to: Render Images with GDI+</span></span>](../../../../docs/framework/winforms/advanced/how-to-render-images-with-gdi.md)  
 [<span data-ttu-id="fa10f-116">방법: Windows Forms의 그래픽 인쇄</span><span class="sxs-lookup"><span data-stu-id="fa10f-116">How to: Print Graphics in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)
