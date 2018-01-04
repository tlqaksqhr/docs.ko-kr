---
title: "방법: Windows Forms에서 파일과 연결된 아이콘 추출"
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
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a5153f6389c4477a18c647d7cdaf7b49b43bb7ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="9b72f-102">방법: Windows Forms에서 파일과 연결된 아이콘 추출</span><span class="sxs-lookup"><span data-stu-id="9b72f-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="9b72f-103">많은 파일을 시각적 연결된 된 파일 형식으로 제공 하는 아이콘 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b72f-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="9b72f-104">예를 들어 Microsoft Word 문서 Word 문서를 식별 하는 아이콘을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b72f-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="9b72f-105">Table 컨트롤 또는 목록 컨트롤에 파일을 표시할 때 각 파일 이름 옆에 있는 파일 형식을 나타내는 아이콘을 표시 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b72f-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="9b72f-106">사용 하 여이 작업을 쉽게 수행할 수 있습니다는 <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="9b72f-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b72f-107">예</span><span class="sxs-lookup"><span data-stu-id="9b72f-107">Example</span></span>  
 <span data-ttu-id="9b72f-108">파일과 연결 된 아이콘 추출 하 고 파일 이름 및 연결 된 아이콘을 표시 하는 방법은 다음 코드 예제는 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b72f-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9b72f-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9b72f-109">Compiling the Code</span></span>  
 <span data-ttu-id="9b72f-110">예제를 컴파일하려면:</span><span class="sxs-lookup"><span data-stu-id="9b72f-110">To compile the example:</span></span>  
  
-   <span data-ttu-id="9b72f-111">Windows Form 및 호출에 앞의 코드를 붙여는 `ExtractAssociatedIconExample` 폼의 생성자에서 메서드 또는 <xref:System.Windows.Forms.Form.Load> 이벤트 처리 메서드.</span><span class="sxs-lookup"><span data-stu-id="9b72f-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="9b72f-112">양식에 가져옵니다 있는지 확인 해야 합니다는 <xref:System.IO> 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9b72f-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b72f-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9b72f-113">See Also</span></span>  
 [<span data-ttu-id="9b72f-114">이미지, 비트맵 및 메타파일</span><span class="sxs-lookup"><span data-stu-id="9b72f-114">Images, Bitmaps, and Metafiles</span></span>](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [<span data-ttu-id="9b72f-115">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9b72f-115">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
