---
title: AssemblyOptions 열거형
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3926a0d49b2db02cf52a3cc943b05edc4cc36a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33406287"
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="672b6-102">AssemblyOptions 열거형</span><span class="sxs-lookup"><span data-stu-id="672b6-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="672b6-103">어셈블리 옵션을 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="672b6-104">구문</span><span class="sxs-lookup"><span data-stu-id="672b6-104">Syntax</span></span>  
  
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
  
## <a name="fields"></a><span data-ttu-id="672b6-105">필드</span><span class="sxs-lookup"><span data-stu-id="672b6-105">Fields</span></span>  
  
|<span data-ttu-id="672b6-106">필드</span><span class="sxs-lookup"><span data-stu-id="672b6-106">Field</span></span>|<span data-ttu-id="672b6-107">설명</span><span class="sxs-lookup"><span data-stu-id="672b6-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="672b6-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="672b6-108">optAssemTitle</span></span>|<span data-ttu-id="672b6-109">문자열-어셈블리 제목을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="672b6-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="672b6-110">optAssemDescription</span></span>|<span data-ttu-id="672b6-111">문자열-어셈블리 파일에 대 한 설명을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="672b6-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="672b6-112">optAssemConfig</span></span>|<span data-ttu-id="672b6-113">문자열-어셈블리 구성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="672b6-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="672b6-114">optAssemOS</span></span>|<span data-ttu-id="672b6-115">문자열-로 인코딩된: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion"입니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="672b6-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="672b6-116">optAssemProcessor</span></span>|<span data-ttu-id="672b6-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="672b6-117">ULONG</span></span>|  
|<span data-ttu-id="672b6-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="672b6-118">optAssemLocale</span></span>|<span data-ttu-id="672b6-119">문자열-어셈블리 로캘을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="672b6-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="672b6-120">optAssemVersion</span></span>|<span data-ttu-id="672b6-121">문자열-로 인코딩된: "Major.Minor.Build.Revision".</span><span class="sxs-lookup"><span data-stu-id="672b6-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="672b6-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="672b6-122">optAssemCompany</span></span>|<span data-ttu-id="672b6-123">문자열-회사 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="672b6-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="672b6-124">optAssemProduct</span></span>|<span data-ttu-id="672b6-125">문자열-제품 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="672b6-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="672b6-126">optAssemProductVersion</span></span>|<span data-ttu-id="672b6-127">문자열 (InformationalVersion이 라고도 함)입니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="672b6-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="672b6-128">optAssemCopyright</span></span>|<span data-ttu-id="672b6-129">문자열-저작권 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="672b6-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="672b6-130">optAssemTrademark</span></span>|<span data-ttu-id="672b6-131">문자열-상표 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="672b6-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="672b6-132">optAssemKeyFile</span></span>|<span data-ttu-id="672b6-133">String (파일 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-133">String (file name).</span></span>|  
|<span data-ttu-id="672b6-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="672b6-134">optAssemKeyName</span></span>|<span data-ttu-id="672b6-135">(키 이름) 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-135">String (The key name).</span></span>|  
|<span data-ttu-id="672b6-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="672b6-136">optAssemAlgID</span></span>|<span data-ttu-id="672b6-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="672b6-137">ULONG</span></span>|  
|<span data-ttu-id="672b6-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="672b6-138">optAssemFlags</span></span>|<span data-ttu-id="672b6-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="672b6-139">ULONG</span></span>|  
|<span data-ttu-id="672b6-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="672b6-140">optAssemHalfSign</span></span>|<span data-ttu-id="672b6-141">Bool (DelaySign 라고도 함)입니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="672b6-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="672b6-142">optAssemFileVersion</span></span>|<span data-ttu-id="672b6-143">문자열-"Major.Minor.Build.Revision"-ProductVersion 동일로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="672b6-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="672b6-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="672b6-145">문자열-"Major.Minor.Build.Revision"로 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="672b6-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="672b6-146">optLastAssemOption</span></span>|<span data-ttu-id="672b6-147">요소 수의 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="672b6-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="672b6-148">요구 사항</span><span class="sxs-lookup"><span data-stu-id="672b6-148">Requirements</span></span>  
 <span data-ttu-id="672b6-149">**헤더:** alink.h</span><span class="sxs-lookup"><span data-stu-id="672b6-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="672b6-150">**라이브러리**: alink.dll</span><span class="sxs-lookup"><span data-stu-id="672b6-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="672b6-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="672b6-151">See Also</span></span>  
 [<span data-ttu-id="672b6-152">Al.exe(어셈블리 링커)</span><span class="sxs-lookup"><span data-stu-id="672b6-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)
