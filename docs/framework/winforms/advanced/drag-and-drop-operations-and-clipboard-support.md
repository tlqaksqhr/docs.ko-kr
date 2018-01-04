---
title: "끌어서 놓기 작업 및 클립보드 지원"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- drag and drop [Windows Forms]
- drag and drop [Windows Forms], Windows Forms
- Clipboard [Windows Forms], Windows Forms
ms.assetid: 7cce79b6-5835-46fd-b690-73f12ad368b2
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 27ba3e94e28a1e26d370fa6daf7c93019d1e2428
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="drag-and-drop-operations-and-clipboard-support"></a><span data-ttu-id="68a4e-102">끌어서 놓기 작업 및 클립보드 지원</span><span class="sxs-lookup"><span data-stu-id="68a4e-102">Drag-and-Drop Operations and Clipboard Support</span></span>
<span data-ttu-id="68a4e-103">일련의 이벤트, 특히 <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave> 및 <xref:System.Windows.Forms.Control.DragDrop> 이벤트를 처리하여 Windows 기반 응용 프로그램에서 사용자 끌어서 놓기 작업을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a4e-103">You can enable user drag-and-drop operations within a Windows-based application by handling a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
 <span data-ttu-id="68a4e-104">간단한 메서드 호출을 사용하여 Windows 기반 응용 프로그램 내에서 클립보드로 사용자 데이터 전송 및 사용자 잘라내기/복사/붙여넣기 지원을 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a4e-104">You can also implement user cut/copy/paste support and user data transfer to the Clipboard within your Windows-based applications by using simple method calls.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="68a4e-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="68a4e-105">In This Section</span></span>  
 [<span data-ttu-id="68a4e-106">연습: Windows Forms에서 끌어서 놓기 작업 수행</span><span class="sxs-lookup"><span data-stu-id="68a4e-106">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md)  
 <span data-ttu-id="68a4e-107">끌어서 놓기 작업을 시작하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a4e-107">Explains how to start a drag-and-drop operation.</span></span>  
  
 [<span data-ttu-id="68a4e-108">방법: 응용 프로그램 간에 끌어서 놓기 작업 수행</span><span class="sxs-lookup"><span data-stu-id="68a4e-108">How to: Perform Drag-and-Drop Operations Between Applications</span></span>](../../../../docs/framework/winforms/advanced/how-to-perform-drag-and-drop-operations-between-applications.md)  
 <span data-ttu-id="68a4e-109">응용 프로그램 간에 끌어서 놓기 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68a4e-109">Illustrates how to accomplish drag-and-drop operations across applications.</span></span>  
  
 [<span data-ttu-id="68a4e-110">방법: 클립보드에 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="68a4e-110">How to: Add Data to the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)  
 <span data-ttu-id="68a4e-111">프로그래밍 방식으로 클립보드에 정보를 삽입하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a4e-111">Describes a way to programmatically insert information on the Clipboard.</span></span>  
  
 [<span data-ttu-id="68a4e-112">방법: 클립보드에서 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="68a4e-112">How to: Retrieve Data from the Clipboard</span></span>](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)  
 <span data-ttu-id="68a4e-113">클립보드에 저장된 데이터에 액세스하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a4e-113">Describes how to access the data stored on the Clipboard.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="68a4e-114">관련 단원</span><span class="sxs-lookup"><span data-stu-id="68a4e-114">Related Sections</span></span>  
 [<span data-ttu-id="68a4e-115">Windows Forms에서의 끌어서 놓기 기능</span><span class="sxs-lookup"><span data-stu-id="68a4e-115">Drag-and-Drop Functionality in Windows Forms</span></span>](../../../../docs/framework/winforms/drag-and-drop-functionality-in-windows-forms.md)  
 <span data-ttu-id="68a4e-116">끌어서 놓기 동작을 구현하는 데 사용되는 메서드, 이벤트 및 클래스를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a4e-116">Describes the methods, events, and classes used to implement drag-and-drop behavior.</span></span>  
  
 <xref:System.Windows.Forms.Control.QueryContinueDrag>  
 <span data-ttu-id="68a4e-117">끌기 작업을 계속할 수 있는 권한을 요청하는 이벤트의 복잡성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a4e-117">Describes the intricacies of the event that asks permission to continue the drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Control.DoDragDrop%2A>  
 <span data-ttu-id="68a4e-118">끌기 작업을 시작하는 데 중요한 메서드의 복잡성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="68a4e-118">Describes the intricacies of the method that is central to beginning a drag operation.</span></span>  
  
 <xref:System.Windows.Forms.Clipboard>  
 <span data-ttu-id="68a4e-119">또한 참조 [하는 방법: 활성 MDI 자식으로 데이터 전송](http://msdn.microsoft.com/library/y0hkh2c8\(v=vs.110\))합니다.</span><span class="sxs-lookup"><span data-stu-id="68a4e-119">Also see [How to: Send Data to the Active MDI Child](http://msdn.microsoft.com/library/y0hkh2c8\(v=vs.110\)).</span></span>
