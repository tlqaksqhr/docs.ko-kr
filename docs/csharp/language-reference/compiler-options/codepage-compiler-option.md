---
title: "-codepage(C# 컴파일러 옵션)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /codepage
dev_langs:
- CSharp
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b80f6fcf8891d2f0b921af01cc094f624d807aa1
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="codepage-c-compiler-options"></a><span data-ttu-id="419b3-102">/codepage(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="419b3-102">/codepage (C# Compiler Options)</span></span>
<span data-ttu-id="419b3-103">이 옵션은 필수 페이지가 시스템에 대한 현재 기본 코드 페이지가 아닌 경우 컴파일 중에 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="419b3-103">This option specifies which codepage to use during compilation if the required page is not the current default codepage for the system.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="419b3-104">구문</span><span class="sxs-lookup"><span data-stu-id="419b3-104">Syntax</span></span>  
  
```console  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="419b3-105">인수</span><span class="sxs-lookup"><span data-stu-id="419b3-105">Arguments</span></span>  
 `id`  
 <span data-ttu-id="419b3-106">컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="419b3-106">The id of the code page to use for all source code files in the compilation.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="419b3-107">설명</span><span class="sxs-lookup"><span data-stu-id="419b3-107">Remarks</span></span>  
 <span data-ttu-id="419b3-108">컴퓨터의 기본 코드 페이지를 사용하도록 생성되지 않은 소스 코드 파일을 하나 이상 컴파일할 경우 **/codepage** 옵션을 통해 사용할 코드 페이지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="419b3-108">If you compile one or more source code files that were not created to use the default code page on your computer, you can use the **/codepage** option to specify which code page should be used.</span></span> <span data-ttu-id="419b3-109">**/codepage**는 컴파일에 포함된 모든 소스 코드 파일에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="419b3-109">**/codepage** applies to all source code files in your compilation.</span></span>  
  
 <span data-ttu-id="419b3-110">소스 코드 파일이 컴퓨터에 적용된 것과 동일한 코드 페이지를 사용하여 생성되었거나 소스 코드 파일이 UNICODE 또는 UTF-8을 사용하여 생성된 경우에는 **/codepage**를 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="419b3-110">If the source code files were created with the same codepage that is in effect on your computer or if the source code files were created with UNICODE or UTF-8, you need not use **/codepage**.</span></span>  
  
 <span data-ttu-id="419b3-111">시스템에서 지원되는 코드 페이지를 찾는 방법에 대한 자세한 내용은 [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="419b3-111">See [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371) for information on how to find which code pages are supported on your system.</span></span>  
  
 <span data-ttu-id="419b3-112">이 컴파일러 옵션은 Visual Studio에서 사용할 수 없으며 프로그래밍 방식으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="419b3-112">This compiler option is unavailable in Visual Studio and cannot be changed programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="419b3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="419b3-113">See Also</span></span>  
 <span data-ttu-id="419b3-114">[C# 컴파일러 옵션](../../../csharp/language-reference/compiler-options/index.md) </span><span class="sxs-lookup"><span data-stu-id="419b3-114">[C# Compiler Options](../../../csharp/language-reference/compiler-options/index.md) </span></span>  
 [<span data-ttu-id="419b3-115">프로젝트 및 솔루션 속성 관리</span><span class="sxs-lookup"><span data-stu-id="419b3-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)

