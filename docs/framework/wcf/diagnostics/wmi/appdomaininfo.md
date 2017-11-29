---
title: AppDomainInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6610b7d8-81eb-4bec-a543-9b72ad7b6f73
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 97818cf1fc6fa1c59b8b0eeaab69a73b21360151
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="appdomaininfo"></a><span data-ttu-id="4d9c9-102">AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="4d9c9-102">AppDomainInfo</span></span>
<span data-ttu-id="4d9c9-103">응용 프로그램 도메인 정보</span><span class="sxs-lookup"><span data-stu-id="4d9c9-103">Application domain information</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d9c9-104">구문</span><span class="sxs-lookup"><span data-stu-id="4d9c9-104">Syntax</span></span>  
  
```  
class AppDomainInfo  
{  
  sint32 AppDomainId;  
  boolean IsDefault;  
  boolean LogMalformedMessages;  
  boolean LogMessagesAtServiceLevel;  
  boolean LogMessagesAtTransportLevel;  
  TraceListener MessageLoggingTraceListeners[];  
  string Name;  
  string PerformanceCounters;  
  sint32 ProcessId;  
  string ServiceConfigPath;  
  string TraceLevel;  
  TraceListener wmiTraceListeners[];  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="4d9c9-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4d9c9-105">Methods</span></span>  
 <span data-ttu-id="4d9c9-106">AppDomainInfo 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-106">The AppDomainInfo class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="4d9c9-107">속성</span><span class="sxs-lookup"><span data-stu-id="4d9c9-107">Properties</span></span>  
 <span data-ttu-id="4d9c9-108">AppDomainInfo 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-108">The AppDomainInfo class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="4d9c9-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="4d9c9-109">AppDomainId</span></span>  
 <span data-ttu-id="4d9c9-110">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="4d9c9-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="4d9c9-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4d9c9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d9c9-112">appdomain의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-112">The Id of the appdomain.</span></span>  
  
### <a name="isdefault"></a><span data-ttu-id="4d9c9-113">IsDefault</span><span class="sxs-lookup"><span data-stu-id="4d9c9-113">IsDefault</span></span>  
 <span data-ttu-id="4d9c9-114">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="4d9c9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="4d9c9-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4d9c9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d9c9-116">appdomain이 기본 appdomain인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-116">Indicates whether the appdomain is the default appdomain.</span></span>  
  
### <a name="logmalformedmessages"></a><span data-ttu-id="4d9c9-117">LogMalformedMessages</span><span class="sxs-lookup"><span data-stu-id="4d9c9-117">LogMalformedMessages</span></span>  
 <span data-ttu-id="4d9c9-118">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="4d9c9-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="4d9c9-119">액세스 형식: 읽기/쓰기</span><span class="sxs-lookup"><span data-stu-id="4d9c9-119">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="4d9c9-120">잘못된 형식의 메시지를 기록할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-120">A value that specifies whether malformed messages are logged.</span></span>  
  
### <a name="logmessagesatservicelevel"></a><span data-ttu-id="4d9c9-121">LogMessagesAtServiceLevel</span><span class="sxs-lookup"><span data-stu-id="4d9c9-121">LogMessagesAtServiceLevel</span></span>  
 <span data-ttu-id="4d9c9-122">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="4d9c9-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="4d9c9-123">액세스 형식: 읽기/쓰기</span><span class="sxs-lookup"><span data-stu-id="4d9c9-123">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="4d9c9-124">암호화 및 전송 관련 변환 전에 메시지를 서비스 수준에서 추적할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-124">A value that specifies whether messages are traced at the service level (before encryption and transport-related transforms).</span></span>  
  
### <a name="logmessagesattransportlevel"></a><span data-ttu-id="4d9c9-125">LogMessagesAtTransportLevel</span><span class="sxs-lookup"><span data-stu-id="4d9c9-125">LogMessagesAtTransportLevel</span></span>  
 <span data-ttu-id="4d9c9-126">데이터 형식: boolean</span><span class="sxs-lookup"><span data-stu-id="4d9c9-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="4d9c9-127">액세스 형식: 읽기/쓰기</span><span class="sxs-lookup"><span data-stu-id="4d9c9-127">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="4d9c9-128">메시지를 전송 수준에서 추적할지 여부를 지정하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-128">A value that specifies whether messages are traced at the transport level.</span></span>  
  
### <a name="messageloggingtracelisteners"></a><span data-ttu-id="4d9c9-129">MessageLoggingTraceListeners</span><span class="sxs-lookup"><span data-stu-id="4d9c9-129">MessageLoggingTraceListeners</span></span>  
 <span data-ttu-id="4d9c9-130">데이터 형식: TraceListener 배열</span><span class="sxs-lookup"><span data-stu-id="4d9c9-130">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="4d9c9-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4d9c9-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d9c9-132">System.Wmi.MessageLogging 추적 소스를 수신 대기하는 컬렉션 추적 수신기입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-132">The collection trace listeners that listen to the System.Wmi.MessageLogging trace source.</span></span>  
  
### <a name="name"></a><span data-ttu-id="4d9c9-133">이름</span><span class="sxs-lookup"><span data-stu-id="4d9c9-133">Name</span></span>  
 <span data-ttu-id="4d9c9-134">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="4d9c9-134">Data type: string</span></span>  
  
 <span data-ttu-id="4d9c9-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4d9c9-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d9c9-136">appdomain의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-136">The name of the appdomain.</span></span>  
  
### <a name="performancecounters"></a><span data-ttu-id="4d9c9-137">PerformanceCounters</span><span class="sxs-lookup"><span data-stu-id="4d9c9-137">PerformanceCounters</span></span>  
 <span data-ttu-id="4d9c9-138">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="4d9c9-138">Data type: string</span></span>  
  
 <span data-ttu-id="4d9c9-139">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4d9c9-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d9c9-140">appdomain의 활성 성능 카운터의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-140">The scope of active performance counters in the appdomain.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="4d9c9-141">ProcessId</span><span class="sxs-lookup"><span data-stu-id="4d9c9-141">ProcessId</span></span>  
 <span data-ttu-id="4d9c9-142">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="4d9c9-142">Data type: sint32</span></span>  
  
 <span data-ttu-id="4d9c9-143">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4d9c9-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d9c9-144">프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-144">The process Id.</span></span>  
  
### <a name="serviceconfigpath"></a><span data-ttu-id="4d9c9-145">ServiceConfigPath</span><span class="sxs-lookup"><span data-stu-id="4d9c9-145">ServiceConfigPath</span></span>  
 <span data-ttu-id="4d9c9-146">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="4d9c9-146">Data type: string</span></span>  
  
 <span data-ttu-id="4d9c9-147">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4d9c9-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d9c9-148">서비스의 구성 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-148">The path to the configuration of the service.</span></span>  
  
### <a name="tracelevel"></a><span data-ttu-id="4d9c9-149">TraceLevel</span><span class="sxs-lookup"><span data-stu-id="4d9c9-149">TraceLevel</span></span>  
 <span data-ttu-id="4d9c9-150">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="4d9c9-150">Data type: string</span></span>  
  
 <span data-ttu-id="4d9c9-151">액세스 형식: 읽기/쓰기</span><span class="sxs-lookup"><span data-stu-id="4d9c9-151">Access type: Read/Write</span></span>  
  
 <span data-ttu-id="4d9c9-152">System.Wmi 추적 소스의 추적 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-152">The trace level of the System.Wmi trace source.</span></span>  
  
### <a name="servicemodeltracelisteners"></a><span data-ttu-id="4d9c9-153">ServiceModelTraceListeners</span><span class="sxs-lookup"><span data-stu-id="4d9c9-153">ServiceModelTraceListeners</span></span>  
 <span data-ttu-id="4d9c9-154">데이터 형식: TraceListener 배열</span><span class="sxs-lookup"><span data-stu-id="4d9c9-154">Data type: TraceListener array</span></span>  
  
 <span data-ttu-id="4d9c9-155">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="4d9c9-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="4d9c9-156">System.ServiceModel 추적 소스의 수신기 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-156">A collection of listeners from the System.ServiceModel trace source.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d9c9-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4d9c9-157">Requirements</span></span>  
  
|<span data-ttu-id="4d9c9-158">MOF</span><span class="sxs-lookup"><span data-stu-id="4d9c9-158">MOF</span></span>|<span data-ttu-id="4d9c9-159">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="4d9c9-160">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="4d9c9-160">Namespace</span></span>|<span data-ttu-id="4d9c9-161">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d9c9-161">Defined in root\ServiceModel</span></span>|
