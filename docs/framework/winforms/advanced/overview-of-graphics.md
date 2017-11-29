---
title: "그래픽 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b0a3286cbcaa0eebf59500582a749804b5e1b8ba
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="overview-of-graphics"></a><span data-ttu-id="565c3-102">그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="565c3-102">Overview of Graphics</span></span>
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="565c3-103">응용 프로그래밍 인터페이스 (API)는 Microsoft Windows 운영 체제의 하위 시스템을 구성 하는입니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-103"> is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="565c3-104">화면과 프린터에 정보를 표시 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-104"> is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="565c3-105">이름에서 알 수 있듯이, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]는 이전 버전의 Windows에 포함된 그래픽 장치 인터페이스인 [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]의 후속 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-105">As its name suggests, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] is the successor to [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="565c3-106">관리되는 클래스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="565c3-106">Managed Class Interface</span></span>  
 <span data-ttu-id="565c3-107">[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API 관리 코드로 배포 된 클래스 집합을 통해 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-107">The [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="565c3-108">이 클래스 집합을 라고는 *관리 되는 클래스 인터페이스* 를 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-108">This set of classes is called the *managed class interface* to [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)].</span></span> <span data-ttu-id="565c3-109">다음 네임스페이스는 관리되는 클래스 인터페이스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-109">The following namespaces make up the managed class interface:</span></span>  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="565c3-110">그래픽 장치 인터페이스와 같은 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], 특정 디스플레이 장치의 세부 정보를 염려 하지 않고 화면 또는 프린터에 정보를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-110">With a Graphics Device Interface, such as [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="565c3-111">프로그래머가 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] 클래스에서 제공하는 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-111">The programmer makes calls to methods provided by [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] classes.</span></span> <span data-ttu-id="565c3-112">이러한 메서드가 다시 특정 장치 드라이버에 대한 적절한 호출을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]<span data-ttu-id="565c3-113">는 그래픽 하드웨어에서 응용 프로그램을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-113"> insulates the application from the graphics hardware.</span></span> <span data-ttu-id="565c3-114">이기이는 프로그래머가 장치 독립적인 응용 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="565c3-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="565c3-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="565c3-115">See Also</span></span>  
 [<span data-ttu-id="565c3-116">그래픽 개요</span><span class="sxs-lookup"><span data-stu-id="565c3-116">Graphics Overview</span></span>](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)
