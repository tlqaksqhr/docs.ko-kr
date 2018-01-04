---
title: "이중 버퍼링 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4d83846dcded620b74f7d276fd241a302cce1b60
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="using-double-buffering"></a><span data-ttu-id="cd0c0-102">이중 버퍼링 사용</span><span class="sxs-lookup"><span data-stu-id="cd0c0-102">Using Double Buffering</span></span>
<span data-ttu-id="cd0c0-103">복잡 한 그리기 작업을 포함 하는 응용 프로그램에서 깜빡임을 줄이기 위해 이중 버퍼링 된 그래픽을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="cd0c0-104">.NET Framework에는 이중 버퍼링에 대 한 기본 제공 지원이 포함 되어 있고 관리 그래픽을 수동으로 렌더링 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd0c0-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="cd0c0-105">In This Section</span></span>  
 [<span data-ttu-id="cd0c0-106">이중 버퍼링 그래픽</span><span class="sxs-lookup"><span data-stu-id="cd0c0-106">Double Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/double-buffered-graphics.md)  
 <span data-ttu-id="cd0c0-107">에서는 이중 버퍼링 개념 윤곽선과.NET Framework 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="cd0c0-108">방법: 양식과 컨트롤에 이중 버퍼링을 사용하여 그래픽 깜빡임 줄이기</span><span class="sxs-lookup"><span data-stu-id="cd0c0-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](../../../../docs/framework/winforms/advanced/how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="cd0c0-109">기본 이중 지원.NET Framework의 버퍼링을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="cd0c0-110">방법: 버퍼링된 그래픽 수동 관리</span><span class="sxs-lookup"><span data-stu-id="cd0c0-110">How to: Manually Manage Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="cd0c0-111">응용 프로그램의 이중 버퍼링을 관리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="cd0c0-112">방법: 버퍼링된 그래픽 수동 렌더링</span><span class="sxs-lookup"><span data-stu-id="cd0c0-112">How to: Manually Render Buffered Graphics</span></span>](../../../../docs/framework/winforms/advanced/how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="cd0c0-113">이중 버퍼링 된 그래픽을 렌더링 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cd0c0-114">참조</span><span class="sxs-lookup"><span data-stu-id="cd0c0-114">Reference</span></span>  
 <span data-ttu-id="cd0c0-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span><span class="sxs-lookup"><span data-stu-id="cd0c0-115"><xref:System.Windows.Forms.Control.SetStyle%2A> ,</span></span>  
 <span data-ttu-id="cd0c0-116">이중 버퍼링을 사용 하도록 설정 하는 제어 메서드.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-116">Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="cd0c0-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span><span class="sxs-lookup"><span data-stu-id="cd0c0-117"><xref:System.Drawing.BufferedGraphicsContext> ,</span></span>  
 <span data-ttu-id="cd0c0-118">그래픽 버퍼를 만드는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-118">Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="cd0c0-119">버퍼링 된 그래픽 컨텍스트에 응용 프로그램 도메인에 대 한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cd0c0-119">Provides access to the buffered graphics context for a application domain.</span></span>
