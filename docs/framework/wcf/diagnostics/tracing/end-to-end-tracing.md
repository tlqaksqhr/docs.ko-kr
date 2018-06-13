---
title: 종단 간 추적
ms.date: 03/30/2017
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
ms.openlocfilehash: 733ea0724fdbaea9c7d28ed2a94aba25f67ef87c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474222"
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="3b1e2-102">종단 간 추적</span><span class="sxs-lookup"><span data-stu-id="3b1e2-102">End-to-End Tracing</span></span>
<span data-ttu-id="3b1e2-103">종단 간 (e2e) 추적을 사용 하면 개발자가 Windows Communication Foundation (WCF) 인프라의 용량 계획 및 성능 분석을 위한 추적을 제공 하기 위해 또는 코드 경로가 실패 한 이유를 조사 하는 코드의 실행 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b1e2-103">End to End (e2e) Tracing allows developers to follow the execution of code in the Windows Communication Foundation (WCF) infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> <span data-ttu-id="3b1e2-104">Windows Communication Foundation (WCF) 오류의 원인을 진단 하기 위해 세 가지 상관 관계 메커니즘을 제공: 동작, 전송 및 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1e2-104">Windows Communication Foundation (WCF) provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="3b1e2-105">참조 [종단 간 추적 시나리오](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) 목록은 한 종단 간 추적 시나리오 및의 해당 활동 및 디자인을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1e2-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b1e2-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="3b1e2-106">In This Section</span></span>  
 <span data-ttu-id="3b1e2-107">[활동](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md): Windows Communication Foundation (WCF) 추적 모델의 동작 추적에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1e2-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the Windows Communication Foundation (WCF) tracing model.</span></span>  
  
 <span data-ttu-id="3b1e2-108">[전송](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md): 전송 Windows Communication Foundation (WCF) 추적 모델에 설명 및 사용 하 여 전송 끝점 내의 동작 상호 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1e2-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the Windows Communication Foundation (WCF) tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="3b1e2-109">[전파](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md): 동작 전파에는 WCF Windows Communication Foundation () 모델을 추적 및 전파를 사용 하 여 끝점을 통해 동작을 상호 연결에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b1e2-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the Windows Communication Foundation (WCF) tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="3b1e2-110">추적 형식 요약</span><span class="sxs-lookup"><span data-stu-id="3b1e2-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="3b1e2-111">모든 동작 추적 형식에 대한 요약 제공</span><span class="sxs-lookup"><span data-stu-id="3b1e2-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b1e2-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3b1e2-112">See Also</span></span>  
 [<span data-ttu-id="3b1e2-113">추적 구성</span><span class="sxs-lookup"><span data-stu-id="3b1e2-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="3b1e2-114">Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3b1e2-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="3b1e2-115">종단 간 추적 시나리오</span><span class="sxs-lookup"><span data-stu-id="3b1e2-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [<span data-ttu-id="3b1e2-116">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="3b1e2-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
