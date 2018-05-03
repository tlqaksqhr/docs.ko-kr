---
title: '#pragma checksum(C# 참조)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma checksum'
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 37e06d97b082ba6de75d8efa81723442403e39be
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="2f989-102">#pragma checksum(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="2f989-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="2f989-103">[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 페이지의 디버그를 돕기 위해 소스 파일에 대한 체크섬을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-103">Generates checksums for source files to aid with debugging [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f989-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f989-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2f989-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f989-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="2f989-106">변경 내용이나 업데이트를 모니터링해야 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="2f989-107">해시 알고리즘의 GUID(Globally Unique Identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-107">The Globally Unique Identifier (GUID) for the hash algorithm.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="2f989-108">체크섬의 바이트를 나타내는 16진수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="2f989-109">짝수의 16진수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="2f989-110">홀수를 사용하면 컴파일 시간 경고가 발생하고 지시문이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-110">An odd number of digits results in a compile-time warning, and the directive are ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2f989-111">설명</span><span class="sxs-lookup"><span data-stu-id="2f989-111">Remarks</span></span>  
 <span data-ttu-id="2f989-112">Visual Studio 디버거는 체크섬을 사용하여 항상 올바른 소스를 찾도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="2f989-113">컴파일러는 소스 파일에 대한 체크섬을 계산한 다음 출력을 PDB(프로그램 데이터베이스) 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="2f989-114">그런 다음 디버거는 PDB를 사용하여 소스 파일에 대해 계산하는 체크섬과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="2f989-115">체크섬이 .aspx 파일이 아니라 생성된 소스 파일에 대해 계산되므로 이 솔루션은 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 프로젝트에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-115">This solution does not work for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="2f989-116">이 문제를 해결하기 위해 `#pragma checksum`은 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 페이지에 대한 체크섬 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-116">To address this problem, `#pragma checksum` provides checksum support for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
 <span data-ttu-id="2f989-117">Visual C#에서 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 프로젝트를 만드는 경우 생성된 소스 파일에 소스가 생성되는 .aspx 파일에 대한 체크섬이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-117">When you create an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] project in Visual C#, the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="2f989-118">그런 다음 컴파일러는 PDB 파일에 이 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="2f989-119">컴파일러가 파일에서 `#pragma checksum` 지시문을 발견하지 못하면 체크섬을 계산하고 PDB 파일에 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="2f989-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f989-120">예</span><span class="sxs-lookup"><span data-stu-id="2f989-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{406EA660-64CF-4C82-B6F0-42D48172A799}" "ab007f1d23d9" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f989-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2f989-121">See Also</span></span>  
 [<span data-ttu-id="2f989-122">C# 참조</span><span class="sxs-lookup"><span data-stu-id="2f989-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="2f989-123">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2f989-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="2f989-124">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="2f989-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)
