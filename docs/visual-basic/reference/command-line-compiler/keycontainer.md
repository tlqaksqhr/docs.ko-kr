---
title: "/keycontainer | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- -keycontainer compiler option [Visual Basic]
- keycontainer compiler option [Visual Basic]
- /keycontainer compiler option [Visual Basic]
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: 16
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
ms.openlocfilehash: a783ef85e6ff2b7c6f889f809291ca8c275e709a
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="keycontainer"></a><span data-ttu-id="c6761-102">T:System.Reflection.AssemblyKeyNameAttribute</span><span class="sxs-lookup"><span data-stu-id="c6761-102">/keycontainer</span></span>
<span data-ttu-id="c6761-103">어셈블리에 강력한 이름을 지정하는 키 쌍의 키 컨테이너 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c6761-103">Specifies a key container name for a key pair to give an assembly a strong name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6761-104">구문</span><span class="sxs-lookup"><span data-stu-id="c6761-104">Syntax</span></span>  
  
```  
/keycontainer:container  
```  
  
## <a name="arguments"></a><span data-ttu-id="c6761-105">인수</span><span class="sxs-lookup"><span data-stu-id="c6761-105">Arguments</span></span>  
  
|<span data-ttu-id="c6761-106">용어</span><span class="sxs-lookup"><span data-stu-id="c6761-106">Term</span></span>|<span data-ttu-id="c6761-107">정의</span><span class="sxs-lookup"><span data-stu-id="c6761-107">Definition</span></span>|  
|---|---|  
|`container`|<span data-ttu-id="c6761-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="c6761-108">Required.</span></span> <span data-ttu-id="c6761-109">키가 포함 된 파일의 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="c6761-109">Container file that contains the key.</span></span> <span data-ttu-id="c6761-110">파일 이름을 따옴표로 묶습니다 ("") 이름에 공백이 있는 경우.</span><span class="sxs-lookup"><span data-stu-id="c6761-110">Enclose the file name in quotation marks ("") if the name contains a space.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c6761-111">주의</span><span class="sxs-lookup"><span data-stu-id="c6761-111">Remarks</span></span>  
 <span data-ttu-id="c6761-112">컴파일러는 공개 키를 어셈블리 매니페스트에 삽입 하 고 최종 어셈블리에 개인 키로 서명 하 여 공유할 수 있는 구성 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c6761-112">The compiler creates the sharable component by inserting a public key into the assembly manifest and by signing the final assembly with the private key.</span></span> <span data-ttu-id="c6761-113">키 파일을 생성 하려면 다음을 입력 `sn -k``file` 명령줄에서.</span><span class="sxs-lookup"><span data-stu-id="c6761-113">To generate a key file, type `sn -k``file` at the command line.</span></span> <span data-ttu-id="c6761-114">`-i` 옵션 컨테이너에 키 쌍을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6761-114">The `-i` option installs the key pair into a container.</span></span> <span data-ttu-id="c6761-115">자세한 내용은 [Sn.exe(강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c6761-115">For more information, see [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23).</span></span>  
  
 <span data-ttu-id="c6761-116">로 컴파일할 경우 `/target:module`, 키 파일의 이름이 모듈에 저장 되 고 있는 어셈블리를 컴파일할 때 생성 되는 어셈블리에 통합 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6761-116">If you compile with `/target:module`, the name of the key file is held in the module and incorporated into the assembly that is created when you compile an assembly with [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md).</span></span>  
  
 <span data-ttu-id="c6761-117">사용자 지정 특성으로이 옵션을 지정할 수도 있습니다 (<xref:System.Reflection.AssemblyKeyNameAttribute>) Microsoft MSIL (intermediate language) 모듈에 대 한 소스 코드에서.</xref:System.Reflection.AssemblyKeyNameAttribute></span><span class="sxs-lookup"><span data-stu-id="c6761-117">You can also specify this option as a custom attribute (<xref:System.Reflection.AssemblyKeyNameAttribute>) in the source code for any Microsoft intermediate language (MSIL) module.</span></span>  
  
 <span data-ttu-id="c6761-118">컴파일러에 암호화 정보를 전달할 수도 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c6761-118">You can also pass your encryption information to the compiler with [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md).</span></span> <span data-ttu-id="c6761-119">사용 하 여 [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) 부분적으로 서명 된 어셈블리에 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6761-119">Use [/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md) if you want a partially signed assembly.</span></span>  
  
 <span data-ttu-id="c6761-120">참조 [Creating and using strong-named Assemblies](https://msdn.microsoft.com/library/xwb8f617) 어셈블리 서명에 대 한 자세한 내용은 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6761-120">See [Creating and Using Strong-Named Assemblies](https://msdn.microsoft.com/library/xwb8f617) for more information on signing an assembly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6761-121">`/keycontainer` 옵션은 Visual Studio 개발 환경 내에서 사용할 수 없습니다; 명령줄에서 컴파일할 때에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c6761-121">The `/keycontainer` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6761-122">예제</span><span class="sxs-lookup"><span data-stu-id="c6761-122">Example</span></span>  
 <span data-ttu-id="c6761-123">다음 코드는 소스 파일을 컴파일하 `Input.vb` 하 고 키 컨테이너를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c6761-123">The following code compiles source file `Input.vb` and specifies a key container.</span></span>  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6761-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c6761-124">See Also</span></span>  
 <span data-ttu-id="c6761-125">[어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6761-125">[Assemblies and the Global Assembly Cache](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md) </span></span>  
<span data-ttu-id="c6761-126"> [Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="c6761-126"> [Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="c6761-127"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span><span class="sxs-lookup"><span data-stu-id="c6761-127"> [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) </span></span>  
<span data-ttu-id="c6761-128"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="c6761-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
