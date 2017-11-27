---
title: "추적"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2649eae2-dbf8-421c-9cfb-cfa9e01de87f
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: e0a291e3ca277bc58f69b8016c523b383b3cece8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="tracing"></a><span data-ttu-id="8ee18-102">추적</span><span class="sxs-lookup"><span data-stu-id="8ee18-102">Tracing</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="8ee18-103">에서는 오류 모니터링 및 분석을 위한 응용 프로그램 계측 및 진단 데이터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee18-103"> provides application instrumentation and diagnostic data for fault monitoring and analysis.</span></span> <span data-ttu-id="8ee18-104">응용 프로그램의 작동 방법 또는 오류 발생 원인을 이해하기 위해 디버거 대신 추적을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee18-104">You can use tracing instead of a debugger to understand how an application is behaving, or why it faults.</span></span> <span data-ttu-id="8ee18-105">종단 간 환경을 제공하기 위해 전체 구성 요소에서의 오류와 처리를 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ee18-105">You can also correlate faults and processing across components to provide an end-to-end experience.</span></span>  
  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="8ee18-106">에서는 진단 추적을 위해 다음 데이터를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee18-106"> outputs the following data for diagnostic tracing:</span></span>  
  
-   <span data-ttu-id="8ee18-107">작업 호출, 코드 예외, 경고 및 기타 중요 처리 이벤트 등과 같이 응용 프로그램의 모든 구성 요소에서 프로세스 중요 시점에 대한 추적</span><span class="sxs-lookup"><span data-stu-id="8ee18-107">Traces for process milestones across all components of the applications, such as operation calls, code exceptions, warnings and other significant processing events."</span></span>  
  
-   <span data-ttu-id="8ee18-108">추적 기능 오작동 시 Windows 오류 이벤트.</span><span class="sxs-lookup"><span data-stu-id="8ee18-108">Windows error events when the tracing feature malfunctions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8ee18-109">단원 내용</span><span class="sxs-lookup"><span data-stu-id="8ee18-109">In This Section</span></span>  
 [<span data-ttu-id="8ee18-110">추적 구성</span><span class="sxs-lookup"><span data-stu-id="8ee18-110">Configuring Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/configuring-tracing.md)  
  
 <span data-ttu-id="8ee18-111">이 항목에서는 특정 요구를 충족하기 위해 여러 수준에서 추적을 구성할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee18-111">This topic describes how you can configure tracing at different levels to suit your specific need.</span></span>  
  
 [<span data-ttu-id="8ee18-112">종단 간 추적</span><span class="sxs-lookup"><span data-stu-id="8ee18-112">End-to-End Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/end-to-end-tracing.md)  
  
 <span data-ttu-id="8ee18-113">이 단원에서는 디버깅을 지원하기 위해 종단 간 상관 관계에 대한 동작 추적 및 전파를 사용할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee18-113">This section describes how you can use Activity Tracing and Propagation for end-to-end correlation to assist debugging.</span></span>  
  
 [<span data-ttu-id="8ee18-114">추적을 사용 하 여 응용 프로그램 문제를 해결 하려면</span><span class="sxs-lookup"><span data-stu-id="8ee18-114">Using Tracing to Troubleshoot Your Application</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)  
  
 <span data-ttu-id="8ee18-115">이 단원에서는 응용 프로그램을 디버깅하기 위해 추적을 사용할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee18-115">This section describes how you can use tracing to debug your application.</span></span>  
  
 [<span data-ttu-id="8ee18-116">보안 고려 사항 및 추적에 대 한 유용한 팁</span><span class="sxs-lookup"><span data-stu-id="8ee18-116">Security Concerns and Useful Tips for Tracing</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/security-concerns-and-useful-tips-for-tracing.md)  
  
 <span data-ttu-id="8ee18-117">이 항목에서는 WebHost를 사용할 때의 유용한 팁뿐만 아니라 중요한 정보가 노출되지 않도록 보호할 수 있는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8ee18-117">This topic describes how you can protect sensitive information from being exposed, as well as useful tips when using WebHost.</span></span>  
  
 [<span data-ttu-id="8ee18-118">추적 참조</span><span class="sxs-lookup"><span data-stu-id="8ee18-118">Traces Reference</span></span>](../../../../../docs/framework/wcf/diagnostics/tracing/traces-reference.md)  
  
 <span data-ttu-id="8ee18-119">이 항목에서는 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]에 의해 생성된 모든 추적을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8ee18-119">This topic lists all the traces generated by [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ee18-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8ee18-120">See Also</span></span>  
 [<span data-ttu-id="8ee18-121">Service Trace Viewer 도구(SvcTraceViewer.exe)</span><span class="sxs-lookup"><span data-stu-id="8ee18-121">Service Trace Viewer Tool (SvcTraceViewer.exe)</span></span>](../../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)
