---
title: "IAppIdAuthority 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppIdAuthority
api_location: fusion.dll
api_type: COM
f1_keywords: IAppIdAuthority
helpviewer_keywords: IAppIdAuthority interface [.NET Framework fusion]
ms.assetid: ec354fa1-1efd-41b0-bc43-b90597b6e253
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 07bfd26a43d264babc9854b0fd0da909dd329405
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iappidauthority-interface"></a><span data-ttu-id="93635-102">IAppIdAuthority 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93635-102">IAppIdAuthority Interface</span></span>
<span data-ttu-id="93635-103">생성 하 고 응용 프로그램 id 및 참조에 대 한 키를 비교 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="93635-103">Provides methods that generate and compare keys for application identities and references.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="93635-104">메서드</span><span class="sxs-lookup"><span data-stu-id="93635-104">Methods</span></span>  
  
|<span data-ttu-id="93635-105">메서드</span><span class="sxs-lookup"><span data-stu-id="93635-105">Method</span></span>|<span data-ttu-id="93635-106">설명</span><span class="sxs-lookup"><span data-stu-id="93635-106">Description</span></span>|  
|------------|-----------------|  
|`IAppIdAuthority::AreDefinitionsEqual`|<span data-ttu-id="93635-107">지정 된 두 여부를 나타내는 값을 가져옵니다 [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) 인스턴스는 같습니다.</span><span class="sxs-lookup"><span data-stu-id="93635-107">Gets a value that indicates whether the two specified [IDefinitionAppId](../../../../docs/framework/unmanaged-api/fusion/idefinitionappid-interface.md) instances are equal.</span></span> <span data-ttu-id="93635-108">각 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93635-108">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreReferencesEqual`|<span data-ttu-id="93635-109">지정 된 두 여부를 나타내는 값을 가져옵니다 [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) 인스턴스는 같습니다.</span><span class="sxs-lookup"><span data-stu-id="93635-109">Gets a value that indicates whether the two specified [IReferenceAppId](../../../../docs/framework/unmanaged-api/fusion/ireferenceappid-interface.md) instances are equal.</span></span> <span data-ttu-id="93635-110">각 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93635-110">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualDefinitionsEqual`|<span data-ttu-id="93635-111">두 개의 지정 된 문자열 정의 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93635-111">Gets a value that indicates whether the two specified string definitions are equal.</span></span> <span data-ttu-id="93635-112">각 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93635-112">You can pass the flag value IAPPIDAUTHORITY_ARE_DEFINITIONS_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::AreTextualReferencesEqual`|<span data-ttu-id="93635-113">두 개의 지정 된 문자열 참조 같은지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93635-113">Gets a value that indicates whether the two specified string references are equal.</span></span> <span data-ttu-id="93635-114">각 버전 정보를 무시 하도록 IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION 플래그 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93635-114">You can pass the flag value IAPPIDAUTHORITY_ARE_REFERENCES_EQUAL_FLAG_IGNORE_VERSION to ignore their respective version information.</span></span>|  
|`IAppIdAuthority::CreateDefinition`|<span data-ttu-id="93635-115">새로 생성 된에 대 한 인터페이스 포인터를 가져옵니다 `IDefinitionAppId` 현재 범위에 있는 어셈블리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="93635-115">Gets an interface pointer to a newly generated `IDefinitionAppId` instance that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::CreateReference`|<span data-ttu-id="93635-116">새로 만든 인터페이스 포인터를 가져옵니다 `IReferenceAppId` 현재 범위에 있는 어셈블리를 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="93635-116">Gets an interface pointer to a newly created `IReferenceAppId` that represents the assembly in the current scope.</span></span>|  
|`IAppIdAuthority::DefinitionToText`|<span data-ttu-id="93635-117">지정 된 문자열 버전을 가져옵니다 `IDefinitionAppId`, 지정 된 플래그 값을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="93635-117">Gets a string version of the specified `IDefinitionAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::DoesDefinitionMatchReference`|<span data-ttu-id="93635-118">나타내는 값을 가져옵니다 있는지 여부를 지정 된 `IDefinitionAppId` 및 `IReferenceAppId` 동일한 어셈블리를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="93635-118">Gets a value that indicates whether the specified `IDefinitionAppId` and `IReferenceAppId` represent the same assembly.</span></span>|  
|`IAppIdAuthority::DoesTextualDefinitionMatchTextualReference`|<span data-ttu-id="93635-119">지정한 정의 문자열 및 참조 문자열이 동일한 어셈블리를 나타내는 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93635-119">Gets a value that indicates whether the specified definition string and reference string represent the same assembly.</span></span>|  
|`IAppIdAuthority::GenerateDefinitionKey`|<span data-ttu-id="93635-120">나타내는 지정 된 문자열 키를 가져옵니다 `IDefinitionAppId` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="93635-120">Gets a string key that represents the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::GenerateReferenceKey`|<span data-ttu-id="93635-121">나타내는 지정 된 문자열 키를 가져옵니다 `IReferenceAppId` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="93635-121">Gets a string key that represents the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::HashDefinition`|<span data-ttu-id="93635-122">지정 된 해시 키를 가져옵니다 `IDefinitionAppId` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="93635-122">Gets a hash key for the specified `IDefinitionAppId` instance.</span></span>|  
|`IAppIdAuthority::HashReference`|<span data-ttu-id="93635-123">지정 된 해시 키를 가져옵니다 `IReferenceAppId` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="93635-123">Gets a hash key for the specified `IReferenceAppId` instance.</span></span>|  
|`IAppIdAuthority::ReferenceToText`|<span data-ttu-id="93635-124">지정 된 문자열 버전을 가져옵니다 `IReferenceAppId`, 지정 된 플래그 값을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="93635-124">Gets a string version of the specified `IReferenceAppId`, using the specified flag values.</span></span>|  
|`IAppIdAuthority::TextToDefinition`|<span data-ttu-id="93635-125">한 인터페이스 포인터를 가져옵니다는 `IDefinitionAppId` 지정 된 문자열 키에서 참조 어셈블리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="93635-125">Gets an interface pointer to an `IDefinitionAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
|`IAppIdAuthority::TextToReference`|<span data-ttu-id="93635-126">한 인터페이스 포인터를 가져옵니다는 `IReferenceAppId` 지정 된 문자열 키에서 참조 어셈블리를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="93635-126">Gets an interface pointer to an `IReferenceAppId` instance that represents the assembly referenced by the specified string key.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93635-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93635-127">Requirements</span></span>  
 <span data-ttu-id="93635-128">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="93635-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93635-129">**헤더:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="93635-129">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="93635-130">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93635-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93635-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93635-131">See Also</span></span>  
 [<span data-ttu-id="93635-132">Fusion 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93635-132">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
