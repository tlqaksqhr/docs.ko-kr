---
title: C# 컴파일러 옵션
ms.date: 07/20/2015
f1_keywords:
- cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
ms.openlocfilehash: a0affaf3691d2392c9f8d7502204d0122f2ea428
ms.sourcegitcommit: 77d9a94dac4c05827ed0663d95e0f9ad35d6682e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/24/2018
ms.locfileid: "34472518"
---
# <a name="c-compiler-options"></a><span data-ttu-id="275b3-102">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="275b3-102">C# Compiler Options</span></span>
<span data-ttu-id="275b3-103">컴파일러는 실행 파일(.exe), 동적 연결 라이브러리(.dll) 또는 코드 모듈(.netmodule)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="275b3-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>  
  
 <span data-ttu-id="275b3-104">모든 컴파일러 옵션은 **-옵션** 및 **/옵션**의 두 가지 형태로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="275b3-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="275b3-105">문서에는 **-옵션** 양식만 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="275b3-105">The documentation only shows the **-option** form.</span></span>  
  
 <span data-ttu-id="275b3-106">Visual Studio,에서는 web.config 파일에서 컴파일러 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="275b3-106">In Visual Studio, you set compiler options in the web.config file.</span></span> <span data-ttu-id="275b3-107">자세한 내용은 [\<compiler> 요소](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="275b3-107">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="275b3-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="275b3-108">In This Section</span></span>  
 [<span data-ttu-id="275b3-109">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="275b3-109">Command-line Building With csc.exe</span></span>](command-line-building-with-csc-exe.md)  
 <span data-ttu-id="275b3-110">명령줄에서 Visual C# 응용 프로그램을 빌드하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="275b3-110">Information about building a Visual C# application from the command line.</span></span>  
  
 [<span data-ttu-id="275b3-111">방법: Visual Studio 명령줄에 필요한 환경 변수 설정</span><span class="sxs-lookup"><span data-stu-id="275b3-111">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 <span data-ttu-id="275b3-112">vsvars32.bat를 실행하여 명령줄 빌드를 사용하도록 하는 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="275b3-112">Provides steps for running vsvars32.bat  to enable command-line builds.</span></span>  
  
 [<span data-ttu-id="275b3-113">범주별 C# 컴파일러 옵션 목록</span><span class="sxs-lookup"><span data-stu-id="275b3-113">C# Compiler Options Listed by Category</span></span>](listed-by-category.md)  
 <span data-ttu-id="275b3-114">컴파일러 옵션의 범주별 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="275b3-114">A categorical listing of the compiler options.</span></span>  
  
 [<span data-ttu-id="275b3-115">사전순 C# 컴파일러 옵션 목록</span><span class="sxs-lookup"><span data-stu-id="275b3-115">C# Compiler Options Listed Alphabetically</span></span>](listed-alphabetically.md)  
 <span data-ttu-id="275b3-116">컴파일러 옵션의 사전순 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="275b3-116">An alphabetical listing of the compiler options.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="275b3-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="275b3-117">Related Sections</span></span>  
 [<span data-ttu-id="275b3-118">프로젝트 디자이너, 빌드 페이지</span><span class="sxs-lookup"><span data-stu-id="275b3-118">Build Page, Project Designer</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)  
 <span data-ttu-id="275b3-119">프로젝트가 컴파일, 빌드 및 디버그되는 방법을 제어하는 속성 설정.</span><span class="sxs-lookup"><span data-stu-id="275b3-119">Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="275b3-120">Visual C# 프로젝트의 사용자 지정 빌드 단계에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="275b3-120">Includes information about custom build steps in Visual C# projects.</span></span>  
  
 [<span data-ttu-id="275b3-121">기본 및 사용자 지정 빌드</span><span class="sxs-lookup"><span data-stu-id="275b3-121">Default and Custom Builds</span></span>](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 <span data-ttu-id="275b3-122">빌드 형식 및 구성에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="275b3-122">Information on build types and configurations.</span></span>  
  
 [<span data-ttu-id="275b3-123">빌드 준비 및 관리</span><span class="sxs-lookup"><span data-stu-id="275b3-123">Preparing and Managing Builds</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="275b3-124">Visual Studio 개발 환경 내의 빌드 절차</span><span class="sxs-lookup"><span data-stu-id="275b3-124">Procedures for building within the Visual Studio development environment.</span></span>
