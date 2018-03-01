---
title: "AssemblyOptions 열거형"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- AssemblyOptions
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6ad4f9e02ed0d22009fcb8a5ac078231f2cb22e3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="60cc9-102">AssemblyOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="60cc9-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="60cc9-103">어셈블리 옵션을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60cc9-104">구문</span><span class="sxs-lookup"><span data-stu-id="60cc9-104">Syntax</span></span>  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="60cc9-105">필드</span><span class="sxs-lookup"><span data-stu-id="60cc9-105">Fields</span></span>  
  
|<span data-ttu-id="60cc9-106">필드</span><span class="sxs-lookup"><span data-stu-id="60cc9-106">Field</span></span>|<span data-ttu-id="60cc9-107">설명</span><span class="sxs-lookup"><span data-stu-id="60cc9-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="60cc9-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="60cc9-108">optAssemTitle</span></span>|<span data-ttu-id="60cc9-109">문자열-어셈블리 제목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="60cc9-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="60cc9-110">optAssemDescription</span></span>|<span data-ttu-id="60cc9-111">문자열-어셈블리 파일에 대 한 설명을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="60cc9-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="60cc9-112">optAssemConfig</span></span>|<span data-ttu-id="60cc9-113">문자열-어셈블리 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="60cc9-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="60cc9-114">optAssemOS</span></span>|<span data-ttu-id="60cc9-115">문자열-로 인코딩된: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion"입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="60cc9-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="60cc9-116">optAssemProcessor</span></span>|<span data-ttu-id="60cc9-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="60cc9-117">ULONG</span></span>|  
|<span data-ttu-id="60cc9-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="60cc9-118">optAssemLocale</span></span>|<span data-ttu-id="60cc9-119">문자열-어셈블리 로캘을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="60cc9-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="60cc9-120">optAssemVersion</span></span>|<span data-ttu-id="60cc9-121">문자열-로 인코딩된: "Major.Minor.Build.Revision".</span><span class="sxs-lookup"><span data-stu-id="60cc9-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="60cc9-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="60cc9-122">optAssemCompany</span></span>|<span data-ttu-id="60cc9-123">문자열-회사 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="60cc9-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="60cc9-124">optAssemProduct</span></span>|<span data-ttu-id="60cc9-125">문자열-제품 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="60cc9-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="60cc9-126">optAssemProductVersion</span></span>|<span data-ttu-id="60cc9-127">문자열 (InformationalVersion이 라고도 함)입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="60cc9-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="60cc9-128">optAssemCopyright</span></span>|<span data-ttu-id="60cc9-129">문자열-저작권 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="60cc9-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="60cc9-130">optAssemTrademark</span></span>|<span data-ttu-id="60cc9-131">문자열-상표 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="60cc9-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="60cc9-132">optAssemKeyFile</span></span>|<span data-ttu-id="60cc9-133">String (파일 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-133">String (file name).</span></span>|  
|<span data-ttu-id="60cc9-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="60cc9-134">optAssemKeyName</span></span>|<span data-ttu-id="60cc9-135">(키 이름) 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-135">String (The key name).</span></span>|  
|<span data-ttu-id="60cc9-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="60cc9-136">optAssemAlgID</span></span>|<span data-ttu-id="60cc9-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="60cc9-137">ULONG</span></span>|  
|<span data-ttu-id="60cc9-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="60cc9-138">optAssemFlags</span></span>|<span data-ttu-id="60cc9-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="60cc9-139">ULONG</span></span>|  
|<span data-ttu-id="60cc9-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="60cc9-140">optAssemHalfSign</span></span>|<span data-ttu-id="60cc9-141">Bool (DelaySign 라고도 함)입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="60cc9-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="60cc9-142">optAssemFileVersion</span></span>|<span data-ttu-id="60cc9-143">문자열-"Major.Minor.Build.Revision"-ProductVersion 동일로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="60cc9-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="60cc9-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="60cc9-145">문자열-"Major.Minor.Build.Revision"로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="60cc9-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="60cc9-146">optLastAssemOption</span></span>|<span data-ttu-id="60cc9-147">요소 수의 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="60cc9-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="60cc9-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="60cc9-148">Requirements</span></span>  
 <span data-ttu-id="60cc9-149">**헤더:** alink.h</span><span class="sxs-lookup"><span data-stu-id="60cc9-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="60cc9-150">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="60cc9-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60cc9-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="60cc9-151">See Also</span></span>  
 [<span data-ttu-id="60cc9-152">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="60cc9-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
