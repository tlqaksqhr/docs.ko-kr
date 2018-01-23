---
title: "C# 컴파일러 옵션"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.build.options
helpviewer_keywords:
- compiler options [C#]
- csc.exe
- cl.exe compiler, C# options
- Visual C# compiler
- Visual C#, compiler options
ms.assetid: d3403556-1816-4546-a782-e8223a772e44
caps.latest.revision: "21"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 59000f60acdc8ada11bc5abb9e91b5f53d42b9ae
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="c-compiler-options"></a><span data-ttu-id="8af94-102">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="8af94-102">C# Compiler Options</span></span>
<span data-ttu-id="8af94-103">컴파일러는 실행 파일(.exe), 동적 연결 라이브러리(.dll) 또는 코드 모듈(.netmodule)을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="8af94-103">The compiler produces executable (.exe) files, dynamic-link libraries (.dll), or code modules (.netmodule).</span></span>  
  
 <span data-ttu-id="8af94-104">모든 컴파일러 옵션은 **-옵션** 및 **/옵션**의 두 가지 형태로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af94-104">Every compiler option is available in two forms: **-option** and **/option**.</span></span> <span data-ttu-id="8af94-105">문서에는 **-옵션** 양식만 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8af94-105">The documentation only shows the **-option** form.</span></span>  
  
 <span data-ttu-id="8af94-106">Visual Studio,에서는 web.config 파일에서 컴파일러 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8af94-106">In Visual Studio, you set compiler options in the web.config file.</span></span> <span data-ttu-id="8af94-107">자세한 내용은 [\<compiler> 요소](../../../framework/configure-apps/file-schema/compiler/compiler-element.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8af94-107">For more information, see [\<compiler> Element](../../../framework/configure-apps/file-schema/compiler/compiler-element.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8af94-108">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="8af94-108">In This Section</span></span>  
 [<span data-ttu-id="8af94-109">csc.exe를 사용한 명령줄 빌드</span><span class="sxs-lookup"><span data-stu-id="8af94-109">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)  
 <span data-ttu-id="8af94-110">명령줄에서 Visual C# 응용 프로그램을 빌드하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8af94-110">Information about building a Visual C# application from the command line.</span></span>  
  
 [<span data-ttu-id="8af94-111">방법: Visual Studio 명령줄에 필요한 환경 변수 설정</span><span class="sxs-lookup"><span data-stu-id="8af94-111">How to: Set Environment Variables for the Visual Studio Command Line</span></span>](../../../csharp/language-reference/compiler-options/how-to-set-environment-variables-for-the-visual-studio-command-line.md)  
 <span data-ttu-id="8af94-112">vsvars32.bat를 실행하여 명령줄 빌드를 사용하도록 하는 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8af94-112">Provides steps for running vsvars32.bat  to enable command-line builds.</span></span>  
  
 [<span data-ttu-id="8af94-113">범주별 C# 컴파일러 옵션 목록</span><span class="sxs-lookup"><span data-stu-id="8af94-113">C# Compiler Options Listed by Category</span></span>](../../../csharp/language-reference/compiler-options/listed-by-category.md)  
 <span data-ttu-id="8af94-114">컴파일러 옵션의 범주별 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8af94-114">A categorical listing of the compiler options.</span></span>  
  
 [<span data-ttu-id="8af94-115">사전순 C# 컴파일러 옵션 목록</span><span class="sxs-lookup"><span data-stu-id="8af94-115">C# Compiler Options Listed Alphabetically</span></span>](../../../csharp/language-reference/compiler-options/listed-alphabetically.md)  
 <span data-ttu-id="8af94-116">컴파일러 옵션의 사전순 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8af94-116">An alphabetical listing of the compiler options.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="8af94-117">관련 단원</span><span class="sxs-lookup"><span data-stu-id="8af94-117">Related Sections</span></span>  
 [<span data-ttu-id="8af94-118">프로젝트 디자이너, 빌드 페이지</span><span class="sxs-lookup"><span data-stu-id="8af94-118">Build Page, Project Designer</span></span>](/visualstudio/ide/reference/build-page-project-designer-csharp)  
 <span data-ttu-id="8af94-119">프로젝트가 컴파일, 빌드 및 디버그되는 방법을 제어하는 속성 설정.</span><span class="sxs-lookup"><span data-stu-id="8af94-119">Setting properties that govern how your project is compiled, built, and debugged.</span></span> <span data-ttu-id="8af94-120">Visual C# 프로젝트의 사용자 지정 빌드 단계에 대한 정보를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8af94-120">Includes information about custom build steps in Visual C# projects.</span></span>  
  
 [<span data-ttu-id="8af94-121">기본 및 사용자 지정 빌드</span><span class="sxs-lookup"><span data-stu-id="8af94-121">Default and Custom Builds</span></span>](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 <span data-ttu-id="8af94-122">빌드 형식 및 구성에 대한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="8af94-122">Information on build types and configurations.</span></span>  
  
 [<span data-ttu-id="8af94-123">빌드 준비 및 관리</span><span class="sxs-lookup"><span data-stu-id="8af94-123">Preparing and Managing Builds</span></span>](/visualstudio/ide/building-and-cleaning-projects-and-solutions-in-visual-studio)  
 <span data-ttu-id="8af94-124">Visual Studio 개발 환경 내의 빌드 절차</span><span class="sxs-lookup"><span data-stu-id="8af94-124">Procedures for building within the Visual Studio development environment.</span></span>
