---
title: -결정적
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
- -deterministic compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 273abf8811f04cd7f58599ce3421ca1f17c740d9
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2018
---
# <a name="-deterministic"></a><span data-ttu-id="f36e9-102">-결정적</span><span class="sxs-lookup"><span data-stu-id="f36e9-102">-deterministic</span></span>

<span data-ttu-id="f36e9-103">컴파일러가 해당 바이트에 대 한 출력은 동일한 입력에 대해 컴파일 간에 동일 어셈블리를 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-103">Causes the compiler to produce an assembly whose byte-for-byte output is identical across compilations for identical inputs.</span></span> 

## <a name="syntax"></a><span data-ttu-id="f36e9-104">구문</span><span class="sxs-lookup"><span data-stu-id="f36e9-104">Syntax</span></span>

```
-deterministic
```

## <a name="remarks"></a><span data-ttu-id="f36e9-105">설명</span><span class="sxs-lookup"><span data-stu-id="f36e9-105">Remarks</span></span>

<span data-ttu-id="f36e9-106">기본적으로 컴파일러는 타임 스탬프와 난수에서 생성 되는 GUID를 추가 하므로 지정 된 입력 집합에서 컴파일러 출력은 고유 합니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-106">By default, compiler output from a given set of inputs is unique, since the compiler adds a timestamp and a GUID that is generated from random numbers.</span></span> <span data-ttu-id="f36e9-107">사용 하면는 `-deterministic` 를 생성 하는 옵션을 *결정적 어셈블리*, 동일 하 게 유지 입력으로 해당 이진 콘텐츠는 컴파일 간에 동일 하나.</span><span class="sxs-lookup"><span data-stu-id="f36e9-107">You use the `-deterministic` option to produce a *deterministic assembly*, one whose binary content is identical across compilations as long as the input remains the same.</span></span>

<span data-ttu-id="f36e9-108">컴파일러는 결정성 목적으로 다음 사항을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-108">The compiler considers the following inputs for the purpose of determinism:</span></span>

- <span data-ttu-id="f36e9-109">명령줄 매개 변수 시퀀스입니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-109">The sequence of command-line parameters.</span></span>
- <span data-ttu-id="f36e9-110">컴파일러의.rsp 응답 파일의 내용입니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-110">The contents of the compiler's .rsp response file.</span></span>
- <span data-ttu-id="f36e9-111">을 사용 하는 컴파일러의 정확한 버전 및 참조 되는 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-111">The precise version of the compiler used, and its referenced assemblies.</span></span>
- <span data-ttu-id="f36e9-112">현재 디렉터리 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-112">The current directory path.</span></span>
- <span data-ttu-id="f36e9-113">모든 파일의 이진 내용을 명시적으로 전달 컴파일러에 직접 또는 간접적으로 포함 하 여:</span><span class="sxs-lookup"><span data-stu-id="f36e9-113">The binary contents of all files explicitly passed to the compiler either directly or indirectly, including:</span></span> 
    - <span data-ttu-id="f36e9-114">소스 파일</span><span class="sxs-lookup"><span data-stu-id="f36e9-114">Source files</span></span>
    - <span data-ttu-id="f36e9-115">참조 된 어셈블리</span><span class="sxs-lookup"><span data-stu-id="f36e9-115">Referenced assemblies</span></span>
    - <span data-ttu-id="f36e9-116">참조 된 모듈</span><span class="sxs-lookup"><span data-stu-id="f36e9-116">Referenced modules</span></span>
    - <span data-ttu-id="f36e9-117">자료</span><span class="sxs-lookup"><span data-stu-id="f36e9-117">Resources</span></span>
    - <span data-ttu-id="f36e9-118">강력한 이름 키 파일</span><span class="sxs-lookup"><span data-stu-id="f36e9-118">The strong name key file</span></span>
    - <span data-ttu-id="f36e9-119">@ 응답 파일</span><span class="sxs-lookup"><span data-stu-id="f36e9-119">@ response files</span></span>
    - <span data-ttu-id="f36e9-120">분석기</span><span class="sxs-lookup"><span data-stu-id="f36e9-120">Analyzers</span></span>
    - <span data-ttu-id="f36e9-121">규칙 집합</span><span class="sxs-lookup"><span data-stu-id="f36e9-121">Rulesets</span></span>
    - <span data-ttu-id="f36e9-122">분석기에서 사용할 수 있는 추가 파일</span><span class="sxs-lookup"><span data-stu-id="f36e9-122">Additional files that may be used by analyzers</span></span>
- <span data-ttu-id="f36e9-123">(메시지가 생성 되는 진단 및 예외 언어)에 대 한 현재 culture입니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-123">The current culture (for the language in which diagnostics and exception messages are produced).</span></span>
- <span data-ttu-id="f36e9-124">기본 인코딩은 (또는 현재 코드 페이지) 인코딩을 지정 하지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="f36e9-124">The default encoding (or the current code page) if the encoding is not specified.</span></span>
- <span data-ttu-id="f36e9-125">존재 여부, 존재 하지 않는 및 컴파일러의 검색 경로에 있는 파일의 내용 (예를 들어에 지정 된 `/lib` 또는 `/recurse`).</span><span class="sxs-lookup"><span data-stu-id="f36e9-125">The existence, non-existence, and contents of files on the compiler's search paths (specified, for example, by `/lib` or `/recurse`).</span></span>
- <span data-ttu-id="f36e9-126">컴파일러 실행 되는 CLR 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-126">The CLR platform on which the compiler is run.</span></span>
- <span data-ttu-id="f36e9-127">값 `%LIBPATH%`, 분석기 종속성 로드에 영향을 줄 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-127">The value of `%LIBPATH%`, which can affect analyzer dependency loading.</span></span>

<span data-ttu-id="f36e9-128">공개적으로 사용할 수 있는 원본을 때 결정적 컴파일은 출처를 신뢰할 수 있는 이진 컴파일 되었는지 여부를 설정 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-128">When sources are publicly available, deterministic compilation can be used for establishing whether a binary is compiled from a trusted source.</span></span> <span data-ttu-id="f36e9-129">이진 파일에 대 한 변경에 의존 하는 빌드 단계를 실행 해야 하는지 여부를 확인 하기 위한 연속 빌드 시스템에도 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f36e9-129">It can also be useful in a continuous build system for determining whether build steps that are dependent on changes to a binary need to be executed.</span></span> 

## <a name="see-also"></a><span data-ttu-id="f36e9-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f36e9-130">See Also</span></span>
[<span data-ttu-id="f36e9-131">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="f36e9-131">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
[<span data-ttu-id="f36e9-132">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="f36e9-132">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
