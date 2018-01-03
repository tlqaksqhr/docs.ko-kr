---
title: "어셈블리 &#39;에 필요한 참조 &lt;assemblyidentity&gt;&#39; 포함 형식 &#39;&lt; typename&gt;&#39; 하지만 프로젝트 &#39; 사이의 모호성 때문 적합 한 참조를 찾을 수 없습니다&lt; projectname1&gt;&#39; 및 &#39;&lt; projectname2&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords: BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ca2454f5c306b3defd1c885dfd59ee130f3e828
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a><span data-ttu-id="2655b-102">어셈블리 &#39;에 필요한 참조 &lt;assemblyidentity&gt;&#39; 포함 형식 &#39;&lt; typename&gt;&#39; 하지만 프로젝트 &#39; 사이의 모호성 때문 적합 한 참조를 찾을 수 없습니다&lt; projectname1&gt;&#39; 및 &#39;&lt; projectname2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="2655b-102">Reference required to assembly &#39;&lt;assemblyidentity&gt;&#39; containing type &#39;&lt;typename&gt;&#39;, but a suitable reference could not be found due to ambiguity between projects &#39;&lt;projectname1&gt;&#39; and &#39;&lt;projectname2&gt;&#39;</span></span>
<span data-ttu-id="2655b-103">식은 프로젝트 외부에 정의된 클래스, 구조체, 인터페이스, 열거형 또는 대리자와 같은 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2655b-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="2655b-104">그러나 해당 형식을 정의하는 둘 이상의 어셈블리에 대한 프로젝트 참조가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2655b-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="2655b-105">인용된 프로젝트는 이름이 동일한 어셈블리를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2655b-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="2655b-106">따라서 컴파일러에서 사용자가 액세스하려는 형식에 사용할 어셈블리를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2655b-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="2655b-107">다른 어셈블리에 정의된 형식에 액세스하려면 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 컴파일러에 해당 어셈블리에 대한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2655b-107">To access a type defined in another assembly, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="2655b-108">이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2655b-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="2655b-109">**오류 ID:** BC30969</span><span class="sxs-lookup"><span data-stu-id="2655b-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2655b-110">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="2655b-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="2655b-111">참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="2655b-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="2655b-112">이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2655b-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="2655b-113">프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 파일에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2655b-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2655b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2655b-114">See Also</span></span>  
 [<span data-ttu-id="2655b-115">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="2655b-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="2655b-116">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="2655b-116">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [<span data-ttu-id="2655b-117">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="2655b-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="2655b-118">끊어진 참조 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2655b-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
