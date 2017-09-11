---
title: "#<a name=\"pragma-checksum-c-reference\"></a>pragma checksum(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '#pragma checksum'
dev_langs:
- CSharp
helpviewer_keywords:
- '#pragma checksum [C#]'
ms.assetid: 3673e4ca-6098-4ec1-890f-8fceb2a794a2
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: c48d99843b9ba398dfe8dc3cf0d2264aaf72be9f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="pragma-checksum-c-reference"></a><span data-ttu-id="afe25-102">#pragma checksum(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="afe25-102">#pragma checksum (C# Reference)</span></span>
<span data-ttu-id="afe25-103">[!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 페이지의 디버그를 돕기 위해 소스 파일에 대한 체크섬을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-103">Generates checksums for source files to aid with debugging [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afe25-104">구문</span><span class="sxs-lookup"><span data-stu-id="afe25-104">Syntax</span></span>  
  
```csharp
#pragma checksum "filename" "{guid}" "checksum bytes"  
```  
  
#### <a name="parameters"></a><span data-ttu-id="afe25-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="afe25-105">Parameters</span></span>  
 `"filename"`  
 <span data-ttu-id="afe25-106">변경 내용이나 업데이트를 모니터링해야 하는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-106">The name of the file that requires monitoring for changes or updates.</span></span>  
  
 `"{guid}"`  
 <span data-ttu-id="afe25-107">파일의 GUID(Globally Unique IDentifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-107">The Globally Unique Identifier (GUID) for the file.</span></span>  
  
 `"checksum_bytes"`  
 <span data-ttu-id="afe25-108">체크섬의 바이트를 나타내는 16진수 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-108">The string of hexadecimal digits representing the bytes of the checksum.</span></span> <span data-ttu-id="afe25-109">짝수의 16진수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-109">Must be an even number of hexadecimal digits.</span></span> <span data-ttu-id="afe25-110">홀수를 사용하면 컴파일 시간 경고가 발생하고 지시문이 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-110">An odd number of digits results in a compile-time warning, and the directive are  ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afe25-111">설명</span><span class="sxs-lookup"><span data-stu-id="afe25-111">Remarks</span></span>  
 <span data-ttu-id="afe25-112">Visual Studio 디버거는 체크섬을 사용하여 항상 올바른 소스를 찾도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-112">The Visual Studio debugger uses a checksum to make sure  that it always finds the right source.</span></span> <span data-ttu-id="afe25-113">컴파일러는 소스 파일에 대한 체크섬을 계산한 다음 출력을 PDB(프로그램 데이터베이스) 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-113">The compiler computes the checksum for a source file, and then emits the output to the program database (PDB) file.</span></span> <span data-ttu-id="afe25-114">그런 다음 디버거는 PDB를 사용하여 소스 파일에 대해 계산하는 체크섬과 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-114">The debugger then uses the PDB to compare against the checksum that it computes for the source file.</span></span>  
  
 <span data-ttu-id="afe25-115">체크섬이 .aspx 파일이 아니라 생성된 소스 파일에 대해 계산되므로 이 솔루션은 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 프로젝트에서 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-115">This solution does not work for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] projects, because the computed checksum is for the generated source file, rather than the .aspx file.</span></span> <span data-ttu-id="afe25-116">이 문제를 해결하기 위해 `#pragma checksum`은 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 페이지에 대한 체크섬 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-116">To address this problem, `#pragma checksum` provides checksum support for [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] pages.</span></span>  
  
 <span data-ttu-id="afe25-117">[!INCLUDE[csprcs](~/includes/csprcs-md.md)]에서 [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] 프로젝트를 만드는 경우 생성된 소스 파일에 소스가 생성되는 .aspx 파일에 대한 체크섬이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-117">When you create an [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] project in [!INCLUDE[csprcs](~/includes/csprcs-md.md)], the generated source file contains a checksum for the .aspx file, from which the source is generated.</span></span> <span data-ttu-id="afe25-118">그런 다음 컴파일러는 PDB 파일에 이 정보를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-118">The compiler then writes this information into the PDB file.</span></span>  
  
 <span data-ttu-id="afe25-119">컴파일러가 파일에서 `#pragma checksum` 지시문을 발견하지 못하면 체크섬을 계산하고 PDB 파일에 값을 씁니다.</span><span class="sxs-lookup"><span data-stu-id="afe25-119">If the compiler encounters no `#pragma checksum` directive in the file, it computes the checksum and writes the value to the PDB file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afe25-120">예제</span><span class="sxs-lookup"><span data-stu-id="afe25-120">Example</span></span>  
  
```csharp
class TestClass  
{  
    static int Main()  
    {  
        #pragma checksum "file.cs" "{3673e4ca-6098-4ec1-890f-8fceb2a794a2}" "{012345678AB}" // New checksum  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="afe25-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="afe25-121">See Also</span></span>  
 <span data-ttu-id="afe25-122">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="afe25-122">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="afe25-123">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="afe25-123">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="afe25-124">C# 전처리기 지시문</span><span class="sxs-lookup"><span data-stu-id="afe25-124">C# Preprocessor Directives</span></span>](../../../csharp/language-reference/preprocessor-directives/index.md)

