---
title: "형식의 값 &quot;&lt;typename1&gt;&quot;로 변환할 수 없는&quot;&lt;typename2&gt;&quot; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30955
- bc30955
dev_langs:
- VB
helpviewer_keywords:
- BC30955
ms.assetid: 966b61eb-441e-48b0-bedf-ca95384ecb8b
caps.latest.revision: 12
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
ms.openlocfilehash: 2fbe1550515d2b15a3e349392fc8d78812787ae4
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39"></a><span data-ttu-id="a6a91-102">형식의 값 '&lt;typename1&gt;'로 변환할 수 없는'&lt;typename2&gt;'</span><span class="sxs-lookup"><span data-stu-id="a6a91-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39;</span></span>
<span data-ttu-id="a6a91-103">형식의 값 '\<typename1 > '로 변환할 수 없는 '\<typename2 > '입니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="a6a91-104">형식 불일치 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문일 수 있습니다 '\<assemblyname > '입니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-104">Type mismatch could be due to the mixing of a file reference with a project reference to assembly '\<assemblyname>'.</span></span> <span data-ttu-id="a6a91-105">에 대 한 파일 참조를 교체 '\<파일 경로 > ' 프로젝트에서 '\<projectname1 > '에 대 한 프로젝트와 '\<projectname2 > '입니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-105">Try replacing the file reference to '\<filepath>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="a6a91-106">프로젝트는 프로젝트 참조를 및 파일 참조를 모두 있는 경우에서 컴파일러는 형식 간에 변환할 수 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-106">In a situation where a project makes both a project reference and a file reference, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="a6a91-107">다음 의사 (pseudo) 코드에는이 오류를 생성할 수 있는 상황을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-107">The following pseudo-code illustrates a situation that can generate this error.</span></span>  
  
 `' ================ Visual Basic project P1 ================`  
  
 `'        P1 makes a PROJECT REFERENCE to project P2`  
  
 `'        and a FILE REFERENCE to project P3.`  
  
 `Public commonObject As P3.commonClass`  
  
 `commonObject = P2.getCommonClass()`  
  
 `' ================ Visual Basic project P2 ================`  
  
 `'        P2 makes a PROJECT REFERENCE to project P3`  
  
 `Public Function getCommonClass() As P3.commonClass`  
  
 `Return New P3.commonClass`  
  
 `End Function`  
  
 `' ================ Visual Basic project P3 ================`  
  
 `Public Class commonClass`  
  
 `End Class`  
  
 <span data-ttu-id="a6a91-108">프로젝트 `P1` 프로젝트를 통해 간접 프로젝트 참조를 사용 하면 `P2` 프로젝트에 `P3`에 대 한 직접 파일 참조도 `P3`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-108">Project `P1` makes an indirect project reference through project `P2` to project `P3`, and also a direct file reference to `P3`.</span></span> <span data-ttu-id="a6a91-109">선언 `commonObject` 에 대 한 파일 참조를 사용 하 여 `P3`를 호출 하는 동안 `P2.getCommonClass` 에 대 한 프로젝트 참조를 사용 하 여 `P3`합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-109">The declaration of `commonObject` uses the file reference to `P3`, while the call to `P2.getCommonClass` uses the project reference to `P3`.</span></span>  
  
 <span data-ttu-id="a6a91-110">이 상황에서의 문제점은 파일 참조의 출력 파일의 이름과 파일 경로 지정 한다는 `P3` (일반적으로 p3.dll) 프로젝트 참조 소스 프로젝트를 식별 하는 동안 (`P3`) 프로젝트 이름으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-110">The problem in this situation is that the file reference specifies a file path and name for the output file of `P3` (typically p3.dll), while the project references identify the source project (`P3`) by project name.</span></span> <span data-ttu-id="a6a91-111">이 때문에 컴파일러 보장할 수 없습니다 하는 형식을 `P3.commonClass` 두 개의 다른 참조를 통해 동일한 소스 코드에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-111">Because of this, the compiler cannot guarantee that the type `P3.commonClass` comes from the same source code through the two different references.</span></span>  
  
 <span data-ttu-id="a6a91-112">이 상황은 일반적으로 발생 때 프로젝트 참조와 파일 참조가 섞여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-112">This situation typically occurs when project references and file references are mixed.</span></span> <span data-ttu-id="a6a91-113">앞의 그림에서 문제가 발생 하지 않습니다 `P1` 대 한 직접 프로젝트 참조를 `P3` 파일 참조가 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-113">In the preceding illustration, the problem would not occur if `P1` made a direct project reference to `P3` instead of a file reference.</span></span>  
  
 <span data-ttu-id="a6a91-114">**오류 ID:** BC30955</span><span class="sxs-lookup"><span data-stu-id="a6a91-114">**Error ID:** BC30955</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a6a91-115">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="a6a91-115">To correct this error</span></span>  
  
-   <span data-ttu-id="a6a91-116">프로젝트 참조에 대 한 파일 참조를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a91-116">Change the file reference to a project reference.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a91-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6a91-117">See Also</span></span>  
 <span data-ttu-id="a6a91-118">[Visual Basic의 형식 변환](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="a6a91-118">[Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="a6a91-119"> [프로젝트에서 참조 관리](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="a6a91-119"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="a6a91-120"> [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span><span class="sxs-lookup"><span data-stu-id="a6a91-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span></span>
