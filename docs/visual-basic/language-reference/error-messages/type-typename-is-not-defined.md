---
title: "유형 &quot;&lt;typename&gt;&quot;가 정의 되지 않은 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30002
- bc30002
dev_langs:
- VB
helpviewer_keywords:
- BC30002
ms.assetid: b0faf204-57fd-44de-8c05-9db027eea663
caps.latest.revision: 18
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
ms.openlocfilehash: 55b76e9d080a2e2e9fe6e9737a713524ea6409f6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="type-39lttypenamegt39-is-not-defined"></a><span data-ttu-id="d0d2b-102">유형 '&lt;typename&gt;' 정의 되어 있지 않습니다</span><span class="sxs-lookup"><span data-stu-id="d0d2b-102">Type &#39;&lt;typename&gt;&#39; is not defined</span></span>
<span data-ttu-id="d0d2b-103">문이 정의 되지 않은 형식에 대 한 참조를 했습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d2b-103">The statement has made reference to a type that has not been defined.</span></span> <span data-ttu-id="d0d2b-104">선언문에서와 같은 형식을 정의할 수 `Enum`, `Structure`, `Class`, 또는 `Interface`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d2b-104">You can define a type in a declaration statement such as `Enum`, `Structure`, `Class`, or `Interface`.</span></span>  
  
 <span data-ttu-id="d0d2b-105">**오류 ID:** BC30002</span><span class="sxs-lookup"><span data-stu-id="d0d2b-105">**Error ID:** BC30002</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0d2b-106">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="d0d2b-106">To correct this error</span></span>  
  
-   <span data-ttu-id="d0d2b-107">형식 정 및 참조 둘 다 사용 하는 철자를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d2b-107">Ensure that the type definition and its reference both use the same spelling.</span></span>  
  
-   <span data-ttu-id="d0d2b-108">형식 정의 대 한 참조에 액세스할 수 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d2b-108">Ensure that the type definition is accessible to the reference.</span></span> <span data-ttu-id="d0d2b-109">예를 들어, 형식이 다른 모듈에서 선언 된 경우 `Private`, 참조 하는 모듈로 형식 정의 이동 하거나 선언 `Public`합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d2b-109">For example, if the type is in another module and has been declared `Private`, move the type definition to the referencing module or declare it `Public`.</span></span>  
  
-   <span data-ttu-id="d0d2b-110">형식의 네임 스페이스 프로젝트 내에서 다시 정의 되지 않는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d2b-110">Ensure that the namespace of the type is not redefined within your project.</span></span> <span data-ttu-id="d0d2b-111">인 경우 사용 된 `Global` 형식 이름을 정규화 하는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="d0d2b-111">If it is, use the `Global` keyword to fully qualify the type name.</span></span> <span data-ttu-id="d0d2b-112">예를 들어, 프로젝트 이름은 네임 스페이스를 정의 하는 경우 `System`, <xref:System.Object?displayProperty=fullName>하지 않은 경우 정규화 된 형식에 액세스할 수 없습니다는 `Global` 키워드: `Global.System.Object`.</xref:System.Object?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="d0d2b-112">For example, if a project defines a namespace named `System`, the <xref:System.Object?displayProperty=fullName> type cannot be accessed unless it is fully qualified with the `Global` keyword: `Global.System.Object`.</span></span>  
  
-   <span data-ttu-id="d0d2b-113">형식이 정의 되어 있지만 개체 라이브러리 또는 정의 된 형식 라이브러리에 등록 되지 않은 경우 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], 클릭 **참조 추가** 에 **프로젝트** 메뉴 한 다음 적절 한 개체 라이브러리 또는 형식 라이브러리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d2b-113">If the type is defined, but the object library or type library in which it is defined is not registered in [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], click **Add Reference** on the **Project** menu, and then select the appropriate object library or type library.</span></span>  
  
-   <span data-ttu-id="d0d2b-114">대상된.NET Framework 프로필의 일부인 어셈블리에서 형식 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d2b-114">Ensure that the type is in an assembly that is part of the targeted .NET Framework profile.</span></span> <span data-ttu-id="d0d2b-115">자세한 내용은 참조 [.NET Framework 대상 지정 오류 문제 해결](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors)합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d2b-115">For more information, see [Troubleshooting .NET Framework Targeting Errors](https://docs.microsoft.com/visualstudio/msbuild/troubleshooting-dotnet-framework-targeting-errors).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d2b-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0d2b-116">See Also</span></span>  
 <span data-ttu-id="d0d2b-117">[Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="d0d2b-117">[Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md) </span></span>  
<span data-ttu-id="d0d2b-118"> [Enum 문](../../../visual-basic/language-reference/statements/enum-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d0d2b-118"> [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) </span></span>  
<span data-ttu-id="d0d2b-119"> [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d0d2b-119"> [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md) </span></span>  
<span data-ttu-id="d0d2b-120"> [Class 문](../../../visual-basic/language-reference/statements/class-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d0d2b-120"> [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md) </span></span>  
<span data-ttu-id="d0d2b-121"> [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md) </span><span class="sxs-lookup"><span data-stu-id="d0d2b-121"> [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md) </span></span>  
<span data-ttu-id="d0d2b-122"> [프로젝트의 참조 관리](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)</span><span class="sxs-lookup"><span data-stu-id="d0d2b-122"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project)</span></span>
