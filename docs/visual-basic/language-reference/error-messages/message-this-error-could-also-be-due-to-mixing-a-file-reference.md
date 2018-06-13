---
title: '&lt;메시지&gt; 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문에이 오류도 수 &#39; &lt;assemblyname&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 498ca74497077e3268aa8cb25ce5121f3c9ea59d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588339"
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="57715-102">&lt;메시지&gt; 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문에이 오류도 수 &#39; &lt;assemblyname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="57715-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="57715-103">\<메시지 > 어셈블리에 대 한 프로젝트 참조를 사용 하는 파일 참조가 섞여 있기 때문에이 오류도 수 '\<assemblyname > 합니다.</span><span class="sxs-lookup"><span data-stu-id="57715-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="57715-104">이 경우에 대 한 파일 참조를 바꿔를 보십시오 '\<assemblyfilename >' 프로젝트에서 '\<projectname1 >'에 대 한 프로젝트 참조 '\<projectname2 >'입니다.</span><span class="sxs-lookup"><span data-stu-id="57715-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="57715-105">코드 프로젝트의 다른 프로젝트의 멤버에 액세스 하지만 솔루션의 구성 참조를 해결 하려면 Visual Basic 컴파일러를 허용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57715-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="57715-106">다른 어셈블리에 정의 된 형식에 액세스 하려면 Visual Basic 컴파일러에 해당 어셈블리에 대 한 참조가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57715-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="57715-107">이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57715-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="57715-108">**오류 ID:** BC30971</span><span class="sxs-lookup"><span data-stu-id="57715-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="57715-109">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="57715-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="57715-110">참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="57715-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="57715-111">이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57715-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="57715-112">프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 프로젝트에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57715-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57715-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="57715-113">See Also</span></span>  
 [<span data-ttu-id="57715-114">프로젝트의 참조 관리</span><span class="sxs-lookup"><span data-stu-id="57715-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="57715-115">선언된 요소 참조</span><span class="sxs-lookup"><span data-stu-id="57715-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [<span data-ttu-id="57715-116">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="57715-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="57715-117">끊어진 참조 문제 해결</span><span class="sxs-lookup"><span data-stu-id="57715-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
