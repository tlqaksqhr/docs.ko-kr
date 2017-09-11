---
title: "/baseaddress | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
dev_langs:
- VB
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
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
ms.openlocfilehash: 5687f119a57e0e54eca4df8f91fdf5e8b2775f82
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="baseaddress"></a><span data-ttu-id="25de2-102">/baseaddress</span><span class="sxs-lookup"><span data-stu-id="25de2-102">/baseaddress</span></span>
<span data-ttu-id="25de2-103">DLL을 만들 때 기본 기준 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-103">Specifies a default base address when creating a DLL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25de2-104">구문</span><span class="sxs-lookup"><span data-stu-id="25de2-104">Syntax</span></span>  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a><span data-ttu-id="25de2-105">인수</span><span class="sxs-lookup"><span data-stu-id="25de2-105">Arguments</span></span>  
  
|<span data-ttu-id="25de2-106">용어</span><span class="sxs-lookup"><span data-stu-id="25de2-106">Term</span></span>|<span data-ttu-id="25de2-107">정의</span><span class="sxs-lookup"><span data-stu-id="25de2-107">Definition</span></span>|  
|---|---|  
|`address`|<span data-ttu-id="25de2-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="25de2-108">Required.</span></span> <span data-ttu-id="25de2-109">DLL에 대 한 기본 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-109">The base address for the DLL.</span></span> <span data-ttu-id="25de2-110">이 주소는&16; 진수 숫자로 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-110">This address must be specified as a hexadecimal number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25de2-111">주의</span><span class="sxs-lookup"><span data-stu-id="25de2-111">Remarks</span></span>  
 <span data-ttu-id="25de2-112">DLL에 대 한 기본 기준 주소 설정 되는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-112">The default base address for a DLL is set by the [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span>  
  
 <span data-ttu-id="25de2-113">이 주소의 하위 순서 단어는 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-113">Be aware that the lower-order word in this address is rounded.</span></span> <span data-ttu-id="25de2-114">예를 들어 0x11110001을 지정 하면 0x11110000 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-114">For example, if you specify 0x11110001, it is rounded to 0x11110000.</span></span>  
  
 <span data-ttu-id="25de2-115">DLL에 대 한 서명 프로세스를 완료 하려면 사용 된 `–R` 강력한 이름 도구 (Sn.exe)의 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-115">To complete the signing process for a DLL, use the `–R` option of the Strong Naming tool (Sn.exe).</span></span>  
  
 <span data-ttu-id="25de2-116">대상 DLL이 아닌 경우이 옵션은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-116">This option is ignored if the target is not a DLL.</span></span>  
  
|<span data-ttu-id="25de2-117">Visual Studio IDE에서 /baseaddress를 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="25de2-117">To set /baseaddress in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="25de2-118">1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-118">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="25de2-119">에 **프로젝트** 메뉴를 클릭 하 여 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-119">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="25de2-120">자세한 내용은 [프로젝트 디자이너 소개](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25de2-120">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="25de2-121">2.  클릭 하 고 **컴파일** 탭 합니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="25de2-122">3.  **고급**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-122">3.  Click **Advanced**.</span></span><br /><span data-ttu-id="25de2-123">4.  값을 수정 된 **DLL 기준 주소:** 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-123">4.  Modify the value in the **DLL base address:** box.</span></span> <span data-ttu-id="25de2-124">**참고:** 는 **DLL 기준 주소:** 상자는 읽기 전용 대상 DLL이 아니면 합니다.</span><span class="sxs-lookup"><span data-stu-id="25de2-124">**Note:**      The **DLL base address:** box is read-only unless the target is a DLL.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25de2-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25de2-125">See Also</span></span>  
 <span data-ttu-id="25de2-126">[Visual Basic 명령줄 컴파일러](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="25de2-126">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="25de2-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span><span class="sxs-lookup"><span data-stu-id="25de2-127"> [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) </span></span>  
<span data-ttu-id="25de2-128"> [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="25de2-128"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="25de2-129"> [Sn.exe (강력한 이름 도구)](https://msdn.microsoft.com/library/k5b5tt23)</span><span class="sxs-lookup"><span data-stu-id="25de2-129"> [Sn.exe (Strong Name Tool)](https://msdn.microsoft.com/library/k5b5tt23)</span></span>
