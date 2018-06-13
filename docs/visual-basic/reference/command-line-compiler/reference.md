---
title: -참조 (Visual Basic)
ms.date: 03/13/2018
helpviewer_keywords:
- /reference compiler option [Visual Basic]
- r compiler option [Visual Basic]
- -reference compiler option [Visual Basic]
- /r compiler option [Visual Basic]
- reference compiler option [Visual Basic]
- -r compiler option [Visual Basic]
ms.assetid: 66bdfced-bbf6-43d1-a554-bc0990315737
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb5d3b4c50a9c22880bdcc8406835cf51481e3cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654371"
---
# <a name="-reference-visual-basic"></a><span data-ttu-id="fc64a-102">-참조 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc64a-102">-reference (Visual Basic)</span></span>
<span data-ttu-id="fc64a-103">컴파일러가 지정 된 어셈블리의 형식 정보 현재 컴파일 중인 프로젝트에서 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-103">Causes the compiler to make type information in the specified assemblies available to the project you are currently compiling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc64a-104">구문</span><span class="sxs-lookup"><span data-stu-id="fc64a-104">Syntax</span></span>  
  
```  
-reference:fileList  
' -or-  
-r:fileList  
```  
  
## <a name="arguments"></a><span data-ttu-id="fc64a-105">인수</span><span class="sxs-lookup"><span data-stu-id="fc64a-105">Arguments</span></span>  
  
|<span data-ttu-id="fc64a-106">용어</span><span class="sxs-lookup"><span data-stu-id="fc64a-106">Term</span></span>|<span data-ttu-id="fc64a-107">정의</span><span class="sxs-lookup"><span data-stu-id="fc64a-107">Definition</span></span>|  
|---|---|  
|`fileList`|<span data-ttu-id="fc64a-108">필수.</span><span class="sxs-lookup"><span data-stu-id="fc64a-108">Required.</span></span> <span data-ttu-id="fc64a-109">쉼표로 구분된 어셈블리 파일 이름 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-109">Comma-delimited list of assembly file names.</span></span> <span data-ttu-id="fc64a-110">파일 이름에 공백이 있으면 이름을 따옴표로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-110">If the file name contains a space, enclose the name in quotation marks.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc64a-111">설명</span><span class="sxs-lookup"><span data-stu-id="fc64a-111">Remarks</span></span>  
 <span data-ttu-id="fc64a-112">가져오는 파일 어셈블리 메타 데이터를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-112">The file(s) you import must contain assembly metadata.</span></span> <span data-ttu-id="fc64a-113">Public 형식만 어셈블리 외부에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-113">Only public types are visible outside the assembly.</span></span> <span data-ttu-id="fc64a-114">[/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) 옵션 모듈에서 메타 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-114">The [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md) option imports metadata from a module.</span></span>  
  
 <span data-ttu-id="fc64a-115">어셈블리 (어셈블리 A) 참조 하는 경우는 다른 어셈블리 (어셈블리 B)를 참조 하는 경우를 어셈블리 B를 참조 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-115">If you reference an assembly (Assembly A) which itself references another assembly (Assembly B), you need to reference Assembly B if:</span></span>  
  
-   <span data-ttu-id="fc64a-116">어셈블리 A의 형식은 형식에서 상속되거나 어셈블리 B의 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-116">A type from Assembly A inherits from a type or implements an interface from Assembly B.</span></span>  
  
-   <span data-ttu-id="fc64a-117">어셈블리 B의 반환 형식이나 매개 변수 형식을 사용하는 필드, 속성, 이벤트 또는 메서드가 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-117">A field, property, event, or method that has a return type or parameter type from Assembly B is invoked.</span></span>  
  
 <span data-ttu-id="fc64a-118">사용 하 여 [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) 어셈블리 참조 중 하나 이상이 있는 디렉터리를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-118">Use [-libpath](../../../visual-basic/reference/command-line-compiler/libpath.md) to specify the directory in which one or more of your assembly references is located.</span></span>  
  
 <span data-ttu-id="fc64a-119">어셈블리 (모듈 아님)의 형식을 인식할 수 컴파일러의 경우 해당 형식을 확인할 강제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-119">For the compiler to recognize a type in an assembly (not a module), it must be forced to resolve the type.</span></span> <span data-ttu-id="fc64a-120">이 수행할 수 있는 방법의 한 가지 예는 형식의 인스턴스를 정의 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-120">One example of how you can do this is to define an instance of the type.</span></span> <span data-ttu-id="fc64a-121">다른 방법으로 가지는 컴파일러에 대 한 어셈블리의 형식 이름을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-121">Other ways are available to resolve type names in an assembly for the compiler.</span></span> <span data-ttu-id="fc64a-122">예를 들어, 어셈블리의 형식에서 상속 하는 경우 형식 이름에 알려집니다 컴파일러입니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-122">For example, if you inherit from a type in an assembly, the type name then becomes known to the compiler.</span></span>  
  
 <span data-ttu-id="fc64a-123">참조에서 일반적으로 사용 되는 Vbc.rsp 지시 파일을 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 어셈블리, 기본적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-123">The Vbc.rsp response file, which references commonly used [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] assemblies, is used by default.</span></span> <span data-ttu-id="fc64a-124">사용 하 여 `-noconfig` 컴파일러에서 Vbc.rsp를 사용 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-124">Use `-noconfig` if you do not want the compiler to use Vbc.rsp.</span></span>  
  
 <span data-ttu-id="fc64a-125">`-reference`의 약식은 `/r`입니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-125">The short form of `-reference` is `/r`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc64a-126">예제</span><span class="sxs-lookup"><span data-stu-id="fc64a-126">Example</span></span>  
 <span data-ttu-id="fc64a-127">다음 명령에서는 소스 파일 `Input.vb` 의 어셈블리를 참조 하 고 `Metad1.dll` 및 `Metad2.dll` 되려면 `Out.exe`합니다.</span><span class="sxs-lookup"><span data-stu-id="fc64a-127">The following command compiles source file `Input.vb` and reference assemblies from `Metad1.dll` and `Metad2.dll` to produce `Out.exe`.</span></span>  
  
```console
vbc -reference:metad1.dll,metad2.dll -out:out.exe input.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc64a-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc64a-128">See Also</span></span>  
 [<span data-ttu-id="fc64a-129">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="fc64a-129">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="fc64a-130">-noconfig</span><span class="sxs-lookup"><span data-stu-id="fc64a-130">-noconfig</span></span>](../../../visual-basic/reference/command-line-compiler/noconfig.md)  
 [<span data-ttu-id="fc64a-131">-대상 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc64a-131">-target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="fc64a-132">공용</span><span class="sxs-lookup"><span data-stu-id="fc64a-132">Public</span></span>](../../../visual-basic/language-reference/modifiers/public.md)  
 [<span data-ttu-id="fc64a-133">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="fc64a-133">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
