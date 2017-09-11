---
title: "형식의 값 &quot;&lt;typename1&gt;&quot;로 변환할 수 없는&quot;&lt;typename2&gt;&quot; (으) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30961
- bc30961
dev_langs:
- VB
helpviewer_keywords:
- BC30961
ms.assetid: 8be5aa0d-d236-4ac3-aa9c-5044f9f6562b
caps.latest.revision: 9
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
ms.openlocfilehash: 299cc4bec00a4597a661c5da49135fe3b5357537
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="value-of-type-39lttypename1gt39-cannot-be-converted-to-39lttypename2gt39-multiple-file-references"></a><span data-ttu-id="7f66b-102">형식의 값 '&lt;typename1&gt;'로 변환할 수 없는'&lt;typename2&gt;' (여러 파일 참조)</span><span class="sxs-lookup"><span data-stu-id="7f66b-102">Value of type &#39;&lt;typename1&gt;&#39; cannot be converted to &#39;&lt;typename2&gt;&#39; (Multiple file references)</span></span>
<span data-ttu-id="7f66b-103">형식의 값 '\<typename1 > '로 변환할 수 없는 '\<typename2 > '입니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-103">Value of type '\<typename1>' cannot be converted to '\<typename2>'.</span></span> <span data-ttu-id="7f66b-104">형식 불일치에 대 한 파일 참조가 섞여 때문일 수 있습니다 '\<filepath1 > ' 프로젝트에서 '\<projectname1 > '에 대 한 파일 참조와 '\<filepath2 > ' 프로젝트에서 '\<projectname2 > '입니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-104">Type mismatch could be due to mixing a file reference to '\<filepath1>' in project '\<projectname1>' with a file reference to '\<filepath2>' in project '\<projectname2>'.</span></span> <span data-ttu-id="7f66b-105">두 어셈블리가 동일하면 동일한 대상을 참조하도록 두 참조를 바꿔 보세요.</span><span class="sxs-lookup"><span data-stu-id="7f66b-105">If both assemblies are identical, try replacing these references so both references are from the same location.</span></span>  
  
 <span data-ttu-id="7f66b-106">둘 이상의 파일 참조를 어셈블리에 프로젝트를 사용 하면 여기서 상황에서 컴파일러는 형식 간에 변환할 수 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-106">In a situation where a project makes more than one file reference to an assembly, the compiler cannot guarantee that one type can be converted to another.</span></span>  
  
 <span data-ttu-id="7f66b-107">각 파일 참조 한 파일 경로 프로젝트 (일반적으로 DLL 파일)의 출력 파일 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-107">Each file reference specifies a file path and name for the output file of a project (typically a DLL file).</span></span> <span data-ttu-id="7f66b-108">컴파일러 출력 파일이 같은 원본에서 가져왔는지 또는 동일한 어셈블리의 동일한 버전을 표시 하는 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-108">The compiler cannot guarantee that the output files come from the same source, or that they represent the same version of the same assembly.</span></span> <span data-ttu-id="7f66b-109">따라서 다른 참조의 유형은 같은 형식 또는 다른 하나의 변환할 수 있는지는 보장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-109">Therefore, it cannot guarantee that the types in the different references are the same type, or even that one can be converted to the other.</span></span>  
  
 <span data-ttu-id="7f66b-110">참조 된 어셈블리는 동일한 어셈블리 id를 알고 있는 경우 단일 파일 참조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-110">You can use a single file reference if you know that the referenced assemblies have the same assembly identity.</span></span> <span data-ttu-id="7f66b-111">*어셈블리 ID* 에는 어셈블리 이름, 버전, 공개 키(있는 경우) 및 문화권이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-111">The *assembly identity* includes the assembly's name, version, public key if any, and culture.</span></span> <span data-ttu-id="7f66b-112">이 정보는 어셈블리를 고유하게 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-112">This information uniquely identifies the assembly.</span></span>  
  
 <span data-ttu-id="7f66b-113">**오류 ID:** BC30961</span><span class="sxs-lookup"><span data-stu-id="7f66b-113">**Error ID:** BC30961</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="7f66b-114">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="7f66b-114">To correct this error</span></span>  
  
-   <span data-ttu-id="7f66b-115">참조 된 어셈블리 id가 동일한 어셈블리를 제거 하거나 단일 파일 참조만 되도록 파일 참조 중 하나를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-115">If the referenced assemblies have the same assembly identity, then remove or replace one of the file references so that there is only a single file reference.</span></span>  
  
-   <span data-ttu-id="7f66b-116">참조 된 어셈블리를 동일한 어셈블리 id 없는 경우 형식에서 다른 형식으로 변환 하려고 하지 않도록 코드를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f66b-116">If the referenced assemblies do not have the same assembly identity, then change your code so that it does not attempt to convert a type in one to a type in the other.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f66b-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f66b-117">See Also</span></span>  
 <span data-ttu-id="7f66b-118">[Visual Basic의 형식 변환](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span><span class="sxs-lookup"><span data-stu-id="7f66b-118">[Type Conversions in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md) </span></span>  
<span data-ttu-id="7f66b-119"> [프로젝트에서 참조 관리](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="7f66b-119"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="7f66b-120"> [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span><span class="sxs-lookup"><span data-stu-id="7f66b-120"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)</span></span>
