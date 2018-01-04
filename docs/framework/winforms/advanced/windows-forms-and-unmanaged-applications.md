---
title: "Windows Forms 및 관리되지 않는 응용 프로그램"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2672e8f87b28e81a9aa233cbf0f1b2c24b2239c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="windows-forms-and-unmanaged-applications"></a><span data-ttu-id="dc9f4-102">Windows Forms 및 관리되지 않는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="dc9f4-102">Windows Forms and Unmanaged Applications</span></span>
<span data-ttu-id="dc9f4-103">Windows Forms 응용 프로그램과 컨트롤은 관리되지 않는 응용 프로그램과 상호 운용될 수 있지만 몇 가지 주의할 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc9f4-103">Windows Forms applications and controls can interoperate with unmanaged applications, with some caveats.</span></span> <span data-ttu-id="dc9f4-104">다음 섹션에서는 Windows Forms 응용 프로그램과 컨트롤이 지원하는 시나리오 및 구성과 지원하지 않는 시나리오 및 구성을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9f4-104">The following sections describe the scenarios and configurations that Windows Forms applications and controls support and those that they do not support.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc9f4-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="dc9f4-105">In This Section</span></span>  
 [<span data-ttu-id="dc9f4-106">Windows Forms 및 관리되지 않는 응용 프로그램 개요</span><span class="sxs-lookup"><span data-stu-id="dc9f4-106">Windows Forms and Unmanaged Applications Overview</span></span>](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 <span data-ttu-id="dc9f4-107">관리되지 않는 응용 프로그램에서 작동하는 Windows Forms 컨트롤을 사용 및 구현하는 방법에 대한 일반적인 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9f4-107">Offers general information about how to use and implement Windows Forms controls that work with unmanaged applications.</span></span>  
  
 [<span data-ttu-id="dc9f4-108">방법: ShowDialog 메서드로 Windows Form을 표시하여 COM Interop 지원</span><span class="sxs-lookup"><span data-stu-id="dc9f4-108">How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method</span></span>](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 <span data-ttu-id="dc9f4-109"><xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> 메서드를 사용하여 관리되지 않는 응용 프로그램에서 Windows Form을 실행하는 방법을 보여 주는 코드 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9f4-109">Provides a code example that shows how to use the <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> method to run a Windows Form in an unmanaged application.</span></span>  
  
 [<span data-ttu-id="dc9f4-110">방법: 각 Windows Form을 별개의 스레드에서 표시하여 COM Interop 지원</span><span class="sxs-lookup"><span data-stu-id="dc9f4-110">How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread</span></span>](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 <span data-ttu-id="dc9f4-111">고유한 스레드에서 Windows Form을 실행하는 방법을 보여 주는 코드 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9f4-111">Provides a code example that shows how to run a Windows Form on its own thread.</span></span>  
  
 <span data-ttu-id="dc9f4-112">[연습: 각 Windows Form을 별개의 스레드에서 표시하여 COM Interop 지원](http://msdn.microsoft.com/library/ms233639\(v=vs.110\))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc9f4-112">Also see [Walkthrough: Supporting COM Interop by Displaying Each Windows Form on Its Own Thread](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dc9f4-113">참조</span><span class="sxs-lookup"><span data-stu-id="dc9f4-113">Reference</span></span>  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 <span data-ttu-id="dc9f4-114">Windows Form에 대한 별도 스레드를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc9f4-114">Used to create a separate thread for a Windows Form.</span></span>  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 <span data-ttu-id="dc9f4-115">스레드에 대한 메시지 루프를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9f4-115">Starts a message loop for a thread.</span></span>  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 <span data-ttu-id="dc9f4-116">관리되지 않는 응용 프로그램에서의 폼 호출을 마샬링합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9f4-116">Marshals calls from an unmanaged application to a form.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="dc9f4-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="dc9f4-117">Related Sections</span></span>  
 [<span data-ttu-id="dc9f4-118">.NET Framework 구성 요소를 COM에 노출</span><span class="sxs-lookup"><span data-stu-id="dc9f4-118">Exposing .NET Framework Components to COM</span></span>](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 <span data-ttu-id="dc9f4-119">관리되지 않는 응용 프로그램에서 .NET Framework 형식을 사용하는 방법에 대한 일반적인 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="dc9f4-119">Offers general information about how to use .NET Framework types in unmanaged applications.</span></span>
