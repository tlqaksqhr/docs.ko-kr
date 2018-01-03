---
title: "상수(관리되지 않는 API 참조)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e086e856bb7a872b14815825f78d208ff5296899
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="0584b-102">상수(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="0584b-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="0584b-103">이 항목에서는 언어 유형, 언어 공급 업체 및 CorSym.idl에 정의 된 문서 형식 상수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="0584b-104">언어 형식 상수</span><span class="sxs-lookup"><span data-stu-id="0584b-104">Language Type Constants</span></span>  
 <span data-ttu-id="0584b-105">다음 표에서 언어 프로그래밍 언어를 식별 하는 Guid를 나타내는 형식 상수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="0584b-106">기호</span><span class="sxs-lookup"><span data-stu-id="0584b-106">Symbol</span></span>|<span data-ttu-id="0584b-107">설명</span><span class="sxs-lookup"><span data-stu-id="0584b-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0584b-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="0584b-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="0584b-109">C 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="0584b-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="0584b-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="0584b-111">C + + 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="0584b-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="0584b-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="0584b-113">C# 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="0584b-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="0584b-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="0584b-115">기본 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="0584b-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="0584b-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="0584b-117">Java 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="0584b-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="0584b-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="0584b-119">COBOL 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="0584b-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="0584b-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="0584b-121">파스칼 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="0584b-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="0584b-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="0584b-123">Microsoft MSIL (intermediate language) 어셈블리 코드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="0584b-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="0584b-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="0584b-125">JScript 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="0584b-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="0584b-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="0584b-127">SMC 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="0584b-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="0584b-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="0584b-129">.NET Framework에 대해 설정 된 c + + 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="0584b-130">언어 공급 업체 상수</span><span class="sxs-lookup"><span data-stu-id="0584b-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="0584b-131">다음 표에서 언어 프로그래밍 언어 공급 업체를 식별 하는 Guid를 나타내는 공급 업체 상수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="0584b-132">기호</span><span class="sxs-lookup"><span data-stu-id="0584b-132">Symbol</span></span>|<span data-ttu-id="0584b-133">설명</span><span class="sxs-lookup"><span data-stu-id="0584b-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0584b-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="0584b-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="0584b-135">Microsoft를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="0584b-136">문서 형식 상수</span><span class="sxs-lookup"><span data-stu-id="0584b-136">Document Type Constants</span></span>  
 <span data-ttu-id="0584b-137">다음 표에서 문서 문서 형식을 식별 하는 Guid를 나타내는 형식 상수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="0584b-138">기호</span><span class="sxs-lookup"><span data-stu-id="0584b-138">Symbol</span></span>|<span data-ttu-id="0584b-139">설명</span><span class="sxs-lookup"><span data-stu-id="0584b-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="0584b-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="0584b-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="0584b-141">텍스트 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="0584b-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="0584b-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="0584b-143">텍스트가 아닌 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0584b-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0584b-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0584b-144">See Also</span></span>  
 [<span data-ttu-id="0584b-145">관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="0584b-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
