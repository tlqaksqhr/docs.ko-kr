---
title: -sdkpath
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a25755bcbb8d42124cde531f641a611202ae5a1
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="-sdkpath"></a><span data-ttu-id="3fa5d-102">-sdkpath</span><span class="sxs-lookup"><span data-stu-id="3fa5d-102">-sdkpath</span></span>
<span data-ttu-id="3fa5d-103">Mscorlib.dll 및 Microsoft.VisualBasic.dll의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-103">Specifies the location of mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fa5d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3fa5d-104">Syntax</span></span>  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="3fa5d-105">인수</span><span class="sxs-lookup"><span data-stu-id="3fa5d-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="3fa5d-106">Mscorlib.dll 및 Microsoft.VisualBasic.dll 컴파일에 사용할의 버전이 포함 된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-106">The directory containing the versions of mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="3fa5d-107">이 경로 로드 될 때까지 확인 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="3fa5d-108">디렉터리 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3fa5d-109">설명</span><span class="sxs-lookup"><span data-stu-id="3fa5d-109">Remarks</span></span>  
 <span data-ttu-id="3fa5d-110">이 옵션에는 기본이 아닌 위치에서 mscorlib.dll 및 Microsoft.VisualBasic.dll 파일을 로드 하기 위해 Visual Basic 컴파일러를 지시 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-110">This option tells the Visual Basic compiler to load the mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="3fa5d-111">`-sdkpath` 옵션으로 사용할 수 있도록 설계 된 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-111">The `-sdkpath` option was designed to be used with [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="3fa5d-112">[!INCLUDE[Compact](~/includes/compact-md.md)] 이러한 서로 다른 버전을 사용 하 여 형식 및 장치에서 찾을 수 없는 언어 기능 사용을 방지 하기 위해 라이브러리를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-112">The [!INCLUDE[Compact](~/includes/compact-md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fa5d-113">`-sdkpath` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 경우에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-113">The `-sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="3fa5d-114">`-sdkpath` 장치 Visual Basic 프로젝트를 로드할 때 옵션이 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-114">The `-sdkpath` option is set when a Visual Basic device project is loaded.</span></span>  
  
 <span data-ttu-id="3fa5d-115">해당 컴파일러를 사용 하 여 Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하여 해야 지정할 수는 `-vbruntime` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `-vbruntime` compiler option.</span></span> <span data-ttu-id="3fa5d-116">자세한 내용은 참조 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-116">For more information, see [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fa5d-117">예제</span><span class="sxs-lookup"><span data-stu-id="3fa5d-117">Example</span></span>  
 <span data-ttu-id="3fa5d-118">다음 코드에서는 `Myfile.vb` 와 [!INCLUDE[Compact](~/includes/compact-md.md)]의 기본 설치 디렉터리에 있는 Mscorlib.dll 및 Microsoft.VisualBasic.dll의 버전을 사용 하는 [!INCLUDE[Compact](~/includes/compact-md.md)] C 드라이브에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](~/includes/compact-md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](~/includes/compact-md.md)] on the C drive.</span></span> <span data-ttu-id="3fa5d-119">일반적으로 가장 최신 버전의 사용은 [!INCLUDE[Compact](~/includes/compact-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="3fa5d-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](~/includes/compact-md.md)].</span></span>  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3fa5d-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3fa5d-120">See Also</span></span>  
 [<span data-ttu-id="3fa5d-121">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="3fa5d-121">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="3fa5d-122">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="3fa5d-122">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="3fa5d-123">-netcf</span><span class="sxs-lookup"><span data-stu-id="3fa5d-123">-netcf</span></span>](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [<span data-ttu-id="3fa5d-124">-vbruntime</span><span class="sxs-lookup"><span data-stu-id="3fa5d-124">-vbruntime</span></span>](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
