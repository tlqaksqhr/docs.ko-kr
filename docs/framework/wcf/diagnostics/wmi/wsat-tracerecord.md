---
title: WSAT_TraceRecord
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99bc7f66-1335-40d8-aa68-e754d569dc0d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b4e701c2f0d669a04be7f7235c8ab1edb8ce1612
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="wsattracerecord"></a><span data-ttu-id="69346-102">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="69346-102">WSAT_TraceRecord</span></span>
<span data-ttu-id="69346-103">WSAT_TraceRecord</span><span class="sxs-lookup"><span data-stu-id="69346-103">WSAT_TraceRecord</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69346-104">구문</span><span class="sxs-lookup"><span data-stu-id="69346-104">Syntax</span></span>  
  
```  
class WSAT_TraceRecord : WSAT_TraceEvent  
{  
  object ActivityID;  
  sint32 EventID;  
  string TraceRecord;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="69346-105">메서드</span><span class="sxs-lookup"><span data-stu-id="69346-105">Methods</span></span>  
 <span data-ttu-id="69346-106">WSAT_TraceRecord 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69346-106">The WSAT_TraceRecord class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="69346-107">속성</span><span class="sxs-lookup"><span data-stu-id="69346-107">Properties</span></span>  
 <span data-ttu-id="69346-108">WSAT_TraceRecord 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69346-108">The WSAT_TraceRecord class has the following properties:</span></span>  
  
### <a name="activityid"></a><span data-ttu-id="69346-109">ActivityID</span><span class="sxs-lookup"><span data-stu-id="69346-109">ActivityID</span></span>  
 <span data-ttu-id="69346-110">데이터 형식: object</span><span class="sxs-lookup"><span data-stu-id="69346-110">Data type: object</span></span>  
<span data-ttu-id="69346-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="69346-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="69346-112">추적 레코드의 동작 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="69346-112">The activity ID of the trace record.</span></span>  
  
### <a name="eventid"></a><span data-ttu-id="69346-113">EventID</span><span class="sxs-lookup"><span data-stu-id="69346-113">EventID</span></span>  
 <span data-ttu-id="69346-114">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="69346-114">Data type: sint32</span></span>  
<span data-ttu-id="69346-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="69346-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="69346-116">추적 레코드의 이벤트 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="69346-116">The event ID of the trace record.</span></span>  
  
### <a name="tracerecord"></a><span data-ttu-id="69346-117">TraceRecord</span><span class="sxs-lookup"><span data-stu-id="69346-117">TraceRecord</span></span>  
 <span data-ttu-id="69346-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="69346-118">Data type: string</span></span>  
<span data-ttu-id="69346-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="69346-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="69346-120">추적 레코드</span><span class="sxs-lookup"><span data-stu-id="69346-120">Trace Record</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69346-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69346-121">Requirements</span></span>  
  
|<span data-ttu-id="69346-122">MOF</span><span class="sxs-lookup"><span data-stu-id="69346-122">MOF</span></span>|<span data-ttu-id="69346-123">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69346-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="69346-124">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="69346-124">Namespace</span></span>|<span data-ttu-id="69346-125">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69346-125">Defined in root\ServiceModel</span></span>|
