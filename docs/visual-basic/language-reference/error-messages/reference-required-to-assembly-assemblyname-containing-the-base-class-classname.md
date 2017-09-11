---
title: "참조 어셈블리에 필요한 &quot;&lt;assemblyname&gt;&quot;포함 하는 기본 클래스&quot;&lt;classname&gt;&quot; | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
dev_langs:
- VB
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 131f8fd53fe025ac16450d9ff0019626444c6cc6
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a><span data-ttu-id="25d9d-102">참조 어셈블리에 필요한 '&lt;assemblyname&gt;'포함 하는 기본 클래스'&lt;classname&gt;'</span><span class="sxs-lookup"><span data-stu-id="25d9d-102">Reference required to assembly &#39;&lt;assemblyname&gt;&#39; containing the base class &#39;&lt;classname&gt;&#39;</span></span>
<span data-ttu-id="25d9d-103">참조 어셈블리에 필요한 '\<assemblyname > '의 기본 클래스를 포함 하\<응용 프로그램 이름 > '입니다.</span><span class="sxs-lookup"><span data-stu-id="25d9d-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="25d9d-104">하나를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="25d9d-104">Add one to your project.</span></span>  
  
 <span data-ttu-id="25d9d-105">클래스는 프로젝트에서 직접 참조하지 않는 어셈블리 또는 DLL(동적 연결 라이브러리)에서 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d9d-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="25d9d-106">[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에서는 클래스 둘 이상의 DLL 또는 어셈블리에 정의 되어 있는 경우 모호성을 방지 하기에 대 한 참조를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d9d-106">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>  
  
 <span data-ttu-id="25d9d-107">**오류 ID:** BC30007</span><span class="sxs-lookup"><span data-stu-id="25d9d-107">**Error ID:** BC30007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="25d9d-108">이 오류를 해결하려면</span><span class="sxs-lookup"><span data-stu-id="25d9d-108">To correct this error</span></span>  
  
-   <span data-ttu-id="25d9d-109">참조되지 않은 DLL 또는 어셈블리 이름을 프로젝트 참조에 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="25d9d-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25d9d-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25d9d-110">See Also</span></span>  
 <span data-ttu-id="25d9d-111">[NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="25d9d-111">[NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="25d9d-112"> [프로젝트에서 참조 관리](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="25d9d-112"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="25d9d-113"> [끊어진 참조 문제 해결](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span><span class="sxs-lookup"><span data-stu-id="25d9d-113"> [Troubleshooting Broken References](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span></span>
