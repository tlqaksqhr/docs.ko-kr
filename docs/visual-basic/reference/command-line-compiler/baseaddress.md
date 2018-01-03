---
title: /baseaddress
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1ad39acdec92667fbb0848a1c64c567b504dcb67
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="baseaddress"></a><span data-ttu-id="a47a2-102">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="a47a2-102">/baseaddress</span></span>
<span data-ttu-id="a47a2-103">DLL을 만들 때 기본 기준 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a47a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="a47a2-104">Syntax</span></span>  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="a47a2-105">인수</span><span class="sxs-lookup"><span data-stu-id="a47a2-105">Arguments</span></span>  
  
|<span data-ttu-id="a47a2-106">용어</span><span class="sxs-lookup"><span data-stu-id="a47a2-106">Term</span></span>|<span data-ttu-id="a47a2-107">정의</span><span class="sxs-lookup"><span data-stu-id="a47a2-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="a47a2-108">필수.</span><span class="sxs-lookup"><span data-stu-id="a47a2-108">Required.</span></span> <span data-ttu-id="a47a2-109">DLL의 기준 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-109">The base address for the DLL.</span></span> <span data-ttu-id="a47a2-110">이 주소는 16 진수 숫자로 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a47a2-111">설명</span><span class="sxs-lookup"><span data-stu-id="a47a2-111">Remarks</span></span>  
 <span data-ttu-id="a47a2-112">DLL에 대 한 기본 기준 주소 설정한는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
 <span data-ttu-id="a47a2-113">주의이 주소의 하위 단어 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="a47a2-114">예를 들어 0x11110001를 지정 하면 0x11110000 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="a47a2-115">DLL에 대 한 서명 프로세스를 완료 하려면 사용 된 `–R` 강력한 이름 도구 (Sn.exe)의 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="a47a2-116">대상 DLL이 아닌 경우이 옵션은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="a47a2-117">/Baseaddress Visual Studio IDE에서 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="a47a2-117">To set /baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="a47a2-118">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a47a2-119">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-119">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="a47a2-120">2.  **컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-120">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="a47a2-121">3.  **고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-121">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="a47a2-122">4.  값을 수정 된 **DLL 기준 주소:** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-122">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="a47a2-123">**참고:** 는 **DLL 기준 주소:** 대상 DLL이 아니면 부분은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="a47a2-123">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a47a2-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a47a2-124">See Also</span></span>  
 [<span data-ttu-id="a47a2-125">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="a47a2-125">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a47a2-126">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a47a2-126">/target (Visual Basic)</span></span>](../../../visual-basic/reference/command-line-compiler/target.md)  
 [<span data-ttu-id="a47a2-127">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="a47a2-127">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 <span data-ttu-id="a47a2-128">[Sn.exe (강력한 이름 도구)] [Sn.exe (강력한 이름 도구)](../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="a47a2-128">[Sn.exe (Strong Name Tool)][Sn.exe (Strong Name Tool)](../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
