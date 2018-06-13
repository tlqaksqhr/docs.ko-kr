---
title: 서비스
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: 0cfeb178e26f6c93e29210accf5d7866cc1fca02
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487149"
---
# <a name="service"></a><span data-ttu-id="2558e-102">서비스</span><span class="sxs-lookup"><span data-stu-id="2558e-102">Service</span></span>
<span data-ttu-id="2558e-103">서비스</span><span class="sxs-lookup"><span data-stu-id="2558e-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2558e-104">구문</span><span class="sxs-lookup"><span data-stu-id="2558e-104">Syntax</span></span>  
  
```  
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2558e-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2558e-105">Methods</span></span>  
 <span data-ttu-id="2558e-106">Service 클래스는 메서드를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2558e-107">속성</span><span class="sxs-lookup"><span data-stu-id="2558e-107">Properties</span></span>  
 <span data-ttu-id="2558e-108">Service 클래스에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="2558e-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="2558e-109">BaseAddresses</span></span>  
 <span data-ttu-id="2558e-110">데이터 형식: string array</span><span class="sxs-lookup"><span data-stu-id="2558e-110">Data type: string array</span></span>  
  
 <span data-ttu-id="2558e-111">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-112">서비스가 사용하는 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="2558e-113">동작</span><span class="sxs-lookup"><span data-stu-id="2558e-113">Behaviors</span></span>  
 <span data-ttu-id="2558e-114">데이터 형식: Behavior array</span><span class="sxs-lookup"><span data-stu-id="2558e-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="2558e-115">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-116">이 서비스와 연관된 동작입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="2558e-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="2558e-117">ConfigurationName</span></span>  
 <span data-ttu-id="2558e-118">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="2558e-118">Data type: string</span></span>  
  
 <span data-ttu-id="2558e-119">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="2558e-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="2558e-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="2558e-121">CounterInstanceName</span></span>  
 <span data-ttu-id="2558e-122">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="2558e-122">Data type: string</span></span>  
  
 <span data-ttu-id="2558e-123">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-124">서비스의 성능 카운터 인스턴스의 인스턴스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="2558e-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="2558e-125">DistinguishedName</span></span>  
 <span data-ttu-id="2558e-126">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="2558e-126">Data type: string</span></span>  
  
 <span data-ttu-id="2558e-127">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-128">주소의 서비스 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="2558e-129">확장</span><span class="sxs-lookup"><span data-stu-id="2558e-129">Extensions</span></span>  
 <span data-ttu-id="2558e-130">데이터 형식: string array</span><span class="sxs-lookup"><span data-stu-id="2558e-130">Data type: string array</span></span>  
  
 <span data-ttu-id="2558e-131">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-132">서비스 인스턴스의 확장에 대한 인스턴스 컨텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="2558e-133">메타데이터</span><span class="sxs-lookup"><span data-stu-id="2558e-133">Metadata</span></span>  
 <span data-ttu-id="2558e-134">데이터 형식: string array</span><span class="sxs-lookup"><span data-stu-id="2558e-134">Data type: string array</span></span>  
  
 <span data-ttu-id="2558e-135">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-136">서비스 메타데이터 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="2558e-137">이름</span><span class="sxs-lookup"><span data-stu-id="2558e-137">Name</span></span>  
 <span data-ttu-id="2558e-138">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="2558e-138">Data type: string</span></span>  
  
 <span data-ttu-id="2558e-139">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-140">이 서비스의 고유한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="2558e-141">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="2558e-141">Namespace</span></span>  
 <span data-ttu-id="2558e-142">데이터 형식: string</span><span class="sxs-lookup"><span data-stu-id="2558e-142">Data type: string</span></span>  
  
 <span data-ttu-id="2558e-143">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-144">서비스의 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="2558e-145">Opened</span><span class="sxs-lookup"><span data-stu-id="2558e-145">Opened</span></span>  
 <span data-ttu-id="2558e-146">데이터 형식: datetime</span><span class="sxs-lookup"><span data-stu-id="2558e-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="2558e-147">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-148">서비스가 열린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="2558e-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="2558e-149">OutgoingChannels</span></span>  
 <span data-ttu-id="2558e-150">데이터 형식: Channel array</span><span class="sxs-lookup"><span data-stu-id="2558e-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="2558e-151">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-152">서비스 인스턴스에서 보내는 채널입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="2558e-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="2558e-153">ProcessId</span></span>  
 <span data-ttu-id="2558e-154">데이터 형식: sint32</span><span class="sxs-lookup"><span data-stu-id="2558e-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="2558e-155">액세스 형식: 읽기 전용</span><span class="sxs-lookup"><span data-stu-id="2558e-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2558e-156">서비스를 호스팅하는 프로세스의 프로세스 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2558e-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2558e-157">Requirements</span></span>  
  
|<span data-ttu-id="2558e-158">MOF</span><span class="sxs-lookup"><span data-stu-id="2558e-158">MOF</span></span>|<span data-ttu-id="2558e-159">Servicemodel.mof에 선언되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2558e-160">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="2558e-160">Namespace</span></span>|<span data-ttu-id="2558e-161">root\ServiceModel에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2558e-161">Defined in root\ServiceModel</span></span>|
