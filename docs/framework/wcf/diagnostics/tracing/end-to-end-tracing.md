---
title: "종단 간 추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f5ac7fc7-f97c-4313-b068-54e0c471b2aa
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c3f5c9f80bbf124440952e35049969c7cfa4f19c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="end-to-end-tracing"></a><span data-ttu-id="514c1-102">종단 간 추적</span><span class="sxs-lookup"><span data-stu-id="514c1-102">End-to-End Tracing</span></span>
<span data-ttu-id="514c1-103">E2E(종단 간) 추적을 사용하면 개발자가 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 인프라에서 코드 실행을 추적하여 코드 경로가 실패한 원인을 조사하고 용량 계획 및 성능 분석을 위한 추적 정보를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="514c1-103">End to End (e2e) Tracing allows developers to follow the execution of code in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] infrastructure to investigate why a code path has failed, or to provide detailed tracing for capacity planning and performance analysis.</span></span> [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="514c1-104">에서는 오류의 원인을 진단하는 데 도움이 되는 동작, 전송 및 전파의 세 가지 상관 관계 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="514c1-104"> provides three correlation mechanisms to help diagnose the cause of an error: activities, transfers, and propagation.</span></span>  
  
 <span data-ttu-id="514c1-105">참조 [종단 간 추적 시나리오](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) 목록은 한 종단 간 추적 시나리오 및의 해당 활동 및 디자인을 추적 합니다.</span><span class="sxs-lookup"><span data-stu-id="514c1-105">See [End-To-End Tracing Scenarios](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md) for a list of end-to-end tracing scenarios, and their respective activity and tracing design.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="514c1-106">단원 내용</span><span class="sxs-lookup"><span data-stu-id="514c1-106">In This Section</span></span>  
 <span data-ttu-id="514c1-107">[활동](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md): 설명의 동작 추적에서 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 추적 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="514c1-107">[Activity](../../../../../docs/framework/wcf/diagnostics/tracing/activity.md):  Describes activity traces in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model.</span></span>  
  
 <span data-ttu-id="514c1-108">[전송](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md): 전송에 설명 된 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 모델을 추적 하 고 사용 하 여 끝점 내의 동작 상호 연결 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="514c1-108">[Transfer](../../../../../docs/framework/wcf/diagnostics/tracing/transfer.md):  Describes transfer in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using transfer to correlate activities within endpoints.</span></span>  
  
 <span data-ttu-id="514c1-109">[전파](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md): 설명의 동작 전파는 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 모델, 추적 및 전파를 사용 하 여 끝점을 통해 동작을 상호 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="514c1-109">[Propagation](../../../../../docs/framework/wcf/diagnostics/tracing/propagation.md):  Describes activity propagation in the [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] tracing model, and using propagation to correlate activities across endpoints.</span></span>  
  
 [<span data-ttu-id="514c1-110">추적 형식 요약</span><span class="sxs-lookup"><span data-stu-id="514c1-110">Trace Type Summary</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/trace-type-summary.md)  
  
 <span data-ttu-id="514c1-111">모든 동작 추적 형식에 대한 요약 제공</span><span class="sxs-lookup"><span data-stu-id="514c1-111">Provides a summary of all activity trace types</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="514c1-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="514c1-112">See Also</span></span>  
 [<span data-ttu-id="514c1-113">추적 구성</span><span class="sxs-lookup"><span data-stu-id="514c1-113">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
 [<span data-ttu-id="514c1-114">Service Trace Viewer를 사용하여 상호 관련된 추적 보기 및 문제 해결</span><span class="sxs-lookup"><span data-stu-id="514c1-114">Using Service Trace Viewer for Viewing Correlated Traces and Troubleshooting</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-service-trace-viewer-for-viewing-correlated-traces-and-troubleshooting.md)  
 [<span data-ttu-id="514c1-115">종단 간 추적 시나리오</span><span class="sxs-lookup"><span data-stu-id="514c1-115">End-To-End Tracing Scenarios</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing-scenarios.md)  
 [<span data-ttu-id="514c1-116">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="514c1-116">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
