---
title: 끝점
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 5d597e9e029cec3552c94b47a64dfbf36d933e67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487648"
---
# <a name="endpoint"></a><span data-ttu-id="fd229-102">끝점</span><span class="sxs-lookup"><span data-stu-id="fd229-102">Endpoint</span></span>
<span data-ttu-id="fd229-103">끝점</span><span class="sxs-lookup"><span data-stu-id="fd229-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd229-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd229-104">Syntax</span></span>  
  
```  
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="fd229-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fd229-105">Methods</span></span>  
 <span data-ttu-id="fd229-106">Endpoint 클래스는 다음과 같은 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="fd229-107">메서드</span><span class="sxs-lookup"><span data-stu-id="fd229-107">Method</span></span>|<span data-ttu-id="fd229-108">설명</span><span class="sxs-lookup"><span data-stu-id="fd229-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fd229-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="fd229-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="fd229-110">작업 성능 카운터 인스턴스 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="fd229-111">속성</span><span class="sxs-lookup"><span data-stu-id="fd229-111">Properties</span></span>  
 <span data-ttu-id="fd229-112">Endpoint 클래스에는 다음 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="fd229-113">Address</span><span class="sxs-lookup"><span data-stu-id="fd229-113">Address</span></span>  
 <span data-ttu-id="fd229-114">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="fd229-114">Data type: string</span></span>  
  
 <span data-ttu-id="fd229-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-116">끝점의 주소를 포함하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="fd229-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="fd229-117">AddressHeaders</span></span>  
 <span data-ttu-id="fd229-118">데이터 형식: string array</span><span class="sxs-lookup"><span data-stu-id="fd229-118">Data type: string array</span></span>  
  
 <span data-ttu-id="fd229-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-120">이 끝점에 연결된 주소 헤더의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="fd229-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="fd229-121">AddressIdentity</span></span>  
 <span data-ttu-id="fd229-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="fd229-122">Data type: string</span></span>  
  
 <span data-ttu-id="fd229-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-124">끝점의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="fd229-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="fd229-125">AppDomainId</span></span>  
 <span data-ttu-id="fd229-126">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="fd229-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="fd229-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-128">끝점을 호스트하는 appdomain의 appdomain ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="fd229-129">동작</span><span class="sxs-lookup"><span data-stu-id="fd229-129">Behaviors</span></span>  
 <span data-ttu-id="fd229-130">데이터 형식: Behavior array</span><span class="sxs-lookup"><span data-stu-id="fd229-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="fd229-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-132">이 끝점에서 구현된 동작의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="fd229-133">바인딩</span><span class="sxs-lookup"><span data-stu-id="fd229-133">Binding</span></span>  
 <span data-ttu-id="fd229-134">데이터 형식: Binding</span><span class="sxs-lookup"><span data-stu-id="fd229-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="fd229-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-136">이 끝점에서 사용하는 바인딩입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="fd229-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="fd229-137">ContractName</span></span>  
 <span data-ttu-id="fd229-138">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="fd229-138">Data type: string</span></span>  
  
 <span data-ttu-id="fd229-139">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-140">이 끝점이 공개하는 계약을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="fd229-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="fd229-141">CounterInstanceName</span></span>  
 <span data-ttu-id="fd229-142">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="fd229-142">Data type: string</span></span>  
  
 <span data-ttu-id="fd229-143">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-144">끝점의 성능 카운터 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="fd229-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="fd229-145">ListenUri</span></span>  
 <span data-ttu-id="fd229-146">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="fd229-146">Data type: string</span></span>  
  
 <span data-ttu-id="fd229-147">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-148">끝점이 수신하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="fd229-149">이름</span><span class="sxs-lookup"><span data-stu-id="fd229-149">Name</span></span>  
 <span data-ttu-id="fd229-150">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="fd229-150">Data type: string</span></span>  
  
 <span data-ttu-id="fd229-151">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-152">이 끝점의 고유한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="fd229-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="fd229-153">ProcessId</span></span>  
 <span data-ttu-id="fd229-154">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="fd229-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="fd229-155">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-156">끝점을 호스트하는 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="fd229-157">ref</span><span class="sxs-lookup"><span data-stu-id="fd229-157">ref</span></span>  
 <span data-ttu-id="fd229-158">데이터 형식: Contract</span><span class="sxs-lookup"><span data-stu-id="fd229-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="fd229-159">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="fd229-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="fd229-160">이 끝점이 공개하는 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd229-161">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd229-161">Requirements</span></span>  
  
|<span data-ttu-id="fd229-162">MOF</span><span class="sxs-lookup"><span data-stu-id="fd229-162">MOF</span></span>|<span data-ttu-id="fd229-163">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="fd229-164">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="fd229-164">Namespace</span></span>|<span data-ttu-id="fd229-165">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd229-165">Defined in root\ServiceModel</span></span>|
