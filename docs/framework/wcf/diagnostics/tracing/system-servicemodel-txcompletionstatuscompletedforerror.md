---
title: System.ServiceModel.TxCompletionStatusCompletedForError
ms.date: 03/30/2017
ms.assetid: 8ade4722-a6d5-471c-b960-1cfea4ea2aa9
ms.openlocfilehash: bba41b339d393ad2a02b5be36600927e3548f736
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33484099"
---
# <a name="systemservicemodeltxcompletionstatuscompletedforerror"></a><span data-ttu-id="cb7d9-102">System.ServiceModel.TxCompletionStatusCompletedForError</span><span class="sxs-lookup"><span data-stu-id="cb7d9-102">System.ServiceModel.TxCompletionStatusCompletedForError</span></span>
<span data-ttu-id="cb7d9-103">처리되지 않은 실행 예외로 인해 지정된 작업에 대한 지정된 트랜잭션이 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cb7d9-103">The specified transaction for the specified operation was completed due to an unhandled execution exception.</span></span>  
  
## <a name="description"></a><span data-ttu-id="cb7d9-104">설명</span><span class="sxs-lookup"><span data-stu-id="cb7d9-104">Description</span></span>  
 <span data-ttu-id="cb7d9-105">현재 트랜잭션을 완료하는 동안 오류가 발생하는 경우 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb7d9-105">Traced when an error occurs during an attempt to complete the current transaction.</span></span> <span data-ttu-id="cb7d9-106">이러한 경우는 회신이나 오류가 호출자에게 보내지기 전에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7d9-106">This happens before a reply or fault is sent to the caller.</span></span>  
  
## <a name="troubleshooting"></a><span data-ttu-id="cb7d9-107">문제 해결</span><span class="sxs-lookup"><span data-stu-id="cb7d9-107">Troubleshooting</span></span>  
 <span data-ttu-id="cb7d9-108">예외 메시지 및 실행 가능한 항목에 대한 추적 메시지를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="cb7d9-108">Inspect the traced message for the exception message and any actionable items.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb7d9-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cb7d9-109">See Also</span></span>  
 [<span data-ttu-id="cb7d9-110">추적</span><span class="sxs-lookup"><span data-stu-id="cb7d9-110">Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)  
 [<span data-ttu-id="cb7d9-111">추적을 사용하여 응용 프로그램 문제 해결</span><span class="sxs-lookup"><span data-stu-id="cb7d9-111">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
 [<span data-ttu-id="cb7d9-112">관리 및 진단</span><span class="sxs-lookup"><span data-stu-id="cb7d9-112">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
