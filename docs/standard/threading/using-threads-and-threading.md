---
title: 스레드 및 스레딩 사용
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], about threading
- managed threading
ms.assetid: 9b5ec2cd-121b-4d49-b075-222cf26f2344
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 725a47cae6e3e91cf9e7385427bceece81f3c918
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584182"
---
# <a name="using-threads-and-threading"></a><span data-ttu-id="eab86-102">스레드 및 스레딩 사용</span><span class="sxs-lookup"><span data-stu-id="eab86-102">Using Threads and Threading</span></span>
<span data-ttu-id="eab86-103">이 섹션의 항목에서는 관리되는 스레드의 생성 및 관리에 대해 설명하고, 데이터를 관리되는 스레드로 전달하고 결과를 다시 가져오는 방법, 스레드를 제거하는 방법 그리고 <xref:System.Threading.ThreadAbortException>을 처리하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eab86-103">The topics in this section discuss the creation and management of managed threads, how to pass data to managed threads and get results back, and how to destroy threads and handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="eab86-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="eab86-104">In This Section</span></span>  
 [<span data-ttu-id="eab86-105">스레드 만들기 및 시작할 때 데이터 전달</span><span class="sxs-lookup"><span data-stu-id="eab86-105">Creating Threads and Passing Data at Start Time</span></span>](../../../docs/standard/threading/creating-threads-and-passing-data-at-start-time.md)  
 <span data-ttu-id="eab86-106">데이터를 새 스레드에 전달하는 방법과 데이터를 가져오는 방법을 비롯하여 관리되는 스레드를 만드는 방법을 설명하고 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="eab86-106">Discusses and demonstrates the creation of managed threads, including how to pass data to new threads and how to get data back.</span></span>  
  
 [<span data-ttu-id="eab86-107">스레드 일시 중지 및 다시 시작</span><span class="sxs-lookup"><span data-stu-id="eab86-107">Pausing and Resuming Threads</span></span>](../../../docs/standard/threading/pausing-and-resuming-threads.md)  
 <span data-ttu-id="eab86-108">관리되는 스레드를 일시 중지하고 다시 시작하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eab86-108">Discusses the ramifications of pausing and resuming managed threads.</span></span>  
  
 [<span data-ttu-id="eab86-109">스레드 제거</span><span class="sxs-lookup"><span data-stu-id="eab86-109">Destroying Threads</span></span>](../../../docs/standard/threading/destroying-threads.md)  
 <span data-ttu-id="eab86-110">관리되는 스레드 제거의 결과와 <xref:System.Threading.ThreadAbortException>을 처리하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eab86-110">Discusses the ramifications of destroying managed threads, and how to handle a <xref:System.Threading.ThreadAbortException>.</span></span>  
  
 [<span data-ttu-id="eab86-111">스레드 스케줄링</span><span class="sxs-lookup"><span data-stu-id="eab86-111">Scheduling Threads</span></span>](../../../docs/standard/threading/scheduling-threads.md)  
 <span data-ttu-id="eab86-112">스레드 우선 순위와 스레드 예약에 영향을 미치는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eab86-112">Discusses thread priorities and how they affect thread scheduling.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="eab86-113">참조</span><span class="sxs-lookup"><span data-stu-id="eab86-113">Reference</span></span>  
 <xref:System.Threading.Thread>  
 <span data-ttu-id="eab86-114">비관리 코드에서 가져왔는지 또는 관리되는 응용 프로그램에서 생성되었는지에 관계없이 관리되는 스레드를 나타내는 <xref:System.Threading.Thread> 클래스에 대한 참조 설명서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eab86-114">Provides reference documentation for the <xref:System.Threading.Thread> class, which represents a managed thread, whether it came from unmanaged code or was created in a managed application.</span></span>  
  
 <xref:System.Threading.ThreadStart>  
 <span data-ttu-id="eab86-115">매개 변수가 없는 스레드 프로시저를 나타내는 <xref:System.Threading.ThreadStart> 대리자에 대한 참조 문서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eab86-115">Provides reference documentation for the <xref:System.Threading.ThreadStart> delegate that represents parameterless thread procedures.</span></span>  
  
 <xref:System.Threading.ParameterizedThreadStart>  
 <span data-ttu-id="eab86-116">강력한 형식 지정 없이도 스레드 프로시저에 데이터를 전달할 수 있는 간편한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="eab86-116">Provides an easy way to pass data to a thread procedure, although without strong typing.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="eab86-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="eab86-117">Related Sections</span></span>  
 [<span data-ttu-id="eab86-118">스레드 및 스레딩</span><span class="sxs-lookup"><span data-stu-id="eab86-118">Threads and Threading</span></span>](../../../docs/standard/threading/threads-and-threading.md)  
 <span data-ttu-id="eab86-119">관리되는 스레딩을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="eab86-119">Provides an introduction to managed threading.</span></span>
