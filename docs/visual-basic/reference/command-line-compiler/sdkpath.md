---
title: "/sdkpath | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- sdkpath
- /sdkpath
dev_langs:
- VB
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2e32bb403347063edcf0d47fd4a7511a0da1f340
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="sdkpath"></a><span data-ttu-id="c3a59-102">/sdkpath</span><span class="sxs-lookup"><span data-stu-id="c3a59-102">/sdkpath</span></span>
<span data-ttu-id="c3a59-103">Mscorlib.dll 및 Microsoft.VisualBasic.dll의 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-103">Specifies the location of Mscorlib.dll and Microsoft.VisualBasic.dll.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3a59-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3a59-104">Syntax</span></span>  
  
```  
/sdkpath:path  
```  
  
## <a name="arguments"></a><span data-ttu-id="c3a59-105">인수</span><span class="sxs-lookup"><span data-stu-id="c3a59-105">Arguments</span></span>  
 `path`  
 <span data-ttu-id="c3a59-106">컴파일에 사용 하 여 Mscorlib.dll 및 Microsoft.VisualBasic.dll의 버전이 포함 된 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-106">The directory containing the versions of Mscorlib.dll and Microsoft.VisualBasic.dll to use for compilation.</span></span> <span data-ttu-id="c3a59-107">이 경로 로드 될 때까지 확인 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-107">This path is not verified until it is loaded.</span></span> <span data-ttu-id="c3a59-108">디렉터리 이름을 따옴표로 묶습니다 ("")에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="c3a59-108">Enclose the directory name in quotation marks (" ") if it contains a space.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3a59-109">주의</span><span class="sxs-lookup"><span data-stu-id="c3a59-109">Remarks</span></span>  
 <span data-ttu-id="c3a59-110">이 옵션은 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에 기본이 아닌 위치에서 Mscorlib.dll 및 Microsoft.VisualBasic.dll 파일을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-110">This option tells the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to load the Mscorlib.dll and Microsoft.VisualBasic.dll files from a non-default location.</span></span> <span data-ttu-id="c3a59-111">`/sdkpath` 옵션으로 사용 하도록 설계 되었습니다 [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-111">The `/sdkpath` option was designed to be used with [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md).</span></span> <span data-ttu-id="c3a59-112">[!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] 이러한 서로 다른 버전을 사용 하 여 형식 및 장치에서 찾을 수 없는 언어 기능을 사용 하지 못하도록 하는 라이브러리를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-112">The [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] uses different versions of these support libraries to avoid the use of types and language features not found on the devices.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c3a59-113">`/sdkpath` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-113">The `/sdkpath` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span> <span data-ttu-id="c3a59-114">`/sdkpath` 옵션을 설정 하는 경우는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 장치 프로젝트를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-114">The `/sdkpath` option is set when a [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] device project is loaded.</span></span>  
  
 <span data-ttu-id="c3a59-115">사용 하 여 컴파일러가 Visual Basic 런타임 라이브러리에 대 한 참조 없이 컴파일하도록를 지정할 수는 `/vbruntime` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-115">You can specify that the compiler should compile without a reference to the Visual Basic Runtime Library by using the `/vbruntime` compiler option.</span></span> <span data-ttu-id="c3a59-116">자세한 내용은 참조 [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-116">For more information, see [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c3a59-117">예제</span><span class="sxs-lookup"><span data-stu-id="c3a59-117">Example</span></span>  
 <span data-ttu-id="c3a59-118">다음 코드에서는 `Myfile.vb` 와 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]의 기본 설치 디렉터리에 있는 Mscorlib.dll 및 Microsoft.VisualBasic.dll의 버전을 사용 하는 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] C 드라이브에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-118">The following code compiles `Myfile.vb` with the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)], using the versions of Mscorlib.dll and Microsoft.VisualBasic.dll found in the default installation directory of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)] on the C drive.</span></span> <span data-ttu-id="c3a59-119">가장 최신 버전의 사용은 일반적으로 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="c3a59-119">Typically, you would use the most recent version of the [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact_md.md)].</span></span>  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c3a59-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c3a59-120">See Also</span></span>  
 <span data-ttu-id="c3a59-121">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="c3a59-121">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="c3a59-122"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="c3a59-122"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="c3a59-123"> [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) </span><span class="sxs-lookup"><span data-stu-id="c3a59-123"> [/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md) </span></span>  
<span data-ttu-id="c3a59-124"> [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)</span><span class="sxs-lookup"><span data-stu-id="c3a59-124"> [/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)</span></span>
