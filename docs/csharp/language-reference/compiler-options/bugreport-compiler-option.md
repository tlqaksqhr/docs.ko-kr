---
title: -bugreport(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 5505971ad9a6920124dd4d8c12642a5e4e346322
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-bugreport-c-compiler-options"></a><span data-ttu-id="d9bd3-102">-bugreport(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="d9bd3-102">-bugreport (C# Compiler Options)</span></span>
<span data-ttu-id="d9bd3-103">나중에 분석하기 위해 파일에 디버그 정보를 포함하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-103">Specifies that debug information should be placed in a file for later analysis.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9bd3-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9bd3-104">Syntax</span></span>  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d9bd3-105">인수</span><span class="sxs-lookup"><span data-stu-id="d9bd3-105">Arguments</span></span>  
 `file`  
 <span data-ttu-id="d9bd3-106">버그 보고서를 포함하려는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-106">The name of the file that you want to contain your bug report.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9bd3-107">설명</span><span class="sxs-lookup"><span data-stu-id="d9bd3-107">Remarks</span></span>  
 <span data-ttu-id="d9bd3-108">**-bugreport** 옵션은 `file`에 다음 정보를 포함하도록 지정합니다:</span><span class="sxs-lookup"><span data-stu-id="d9bd3-108">The **-bugreport** option specifies that the following information should be placed in `file`:</span></span>  
  
-   <span data-ttu-id="d9bd3-109">컴파일에 포함된 모든 소스 코드 파일의 복사본입니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-109">A copy of all source code files in the compilation.</span></span>  
  
-   <span data-ttu-id="d9bd3-110">컴파일에 사용된 컴파일러 옵션 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-110">A listing of the compiler options used in the compilation.</span></span>  
  
-   <span data-ttu-id="d9bd3-111">컴파일러, 런타임 및 운영 체제에 대한 버전 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-111">Version information about your compiler, run time, and operating system.</span></span>  
  
-   <span data-ttu-id="d9bd3-112">.NET Framework 및 SDK와 함께 제공되는 어셈블리를 제외하고 16진수로 저장된 참조된 어셈블리 및 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-112">Referenced assemblies and modules, saved as hexadecimal digits, except assemblies that ship with the .NET Framework and SDK.</span></span>  
  
-   <span data-ttu-id="d9bd3-113">컴파일러 출력입니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="d9bd3-113">Compiler output, if any.</span></span>  
  
-   <span data-ttu-id="d9bd3-114">메시지가 표시되는 문제에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-114">A description of the problem, which you will be prompted for.</span></span>  
  
-   <span data-ttu-id="d9bd3-115">메시지가 표시되는 문제 해결 방법에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-115">A description of how you think the problem should be fixed, which you will be prompted for.</span></span>  
  
 <span data-ttu-id="d9bd3-116">**-errorreport:prompt** 또는 **-errorreport:send**와 함께 이 옵션을 사용할 경우 파일의 정보가 Microsoft Corporation에 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-116">If this option is used with **-errorreport:prompt** or **-errorreport:send**, the information in the file will be sent to Microsoft Corporation.</span></span>  
  
 <span data-ttu-id="d9bd3-117">모든 소스 코드 파일의 복사본이 `file`에 저장되기 때문에 최대한 짧은 프로그램으로 의심스러운 코드 결함을 재현하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-117">Because a copy of all source code files will be placed in `file`, you might want to reproduce the suspected code defect in the shortest possible program.</span></span>  
  
 <span data-ttu-id="d9bd3-118">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-118">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
 <span data-ttu-id="d9bd3-119">생성된 파일 내용에 의해 소스 코드가 노출되어, 의도하지 않게 정보가 공개될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9bd3-119">Notice that contents of the generated file expose source code that could result in inadvertent information disclosure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9bd3-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d9bd3-120">See Also</span></span>  
 [<span data-ttu-id="d9bd3-121">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="d9bd3-121">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="d9bd3-122">-errorreport(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="d9bd3-122">-errorreport (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)  
 [<span data-ttu-id="d9bd3-123">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="d9bd3-123">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
