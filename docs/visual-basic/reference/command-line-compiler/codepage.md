---
title: "/codepage (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /codepage compiler option [Visual Basic]
- codepage compiler option [Visual Basic]
- -codepage compiler option [Visual Basic]
ms.assetid: be36ec33-6800-4505-838c-4124564f5cc9
caps.latest.revision: 17
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
ms.openlocfilehash: 6f4919bc4fc8eda700edbd80fead5b5d9fe0dba1
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="codepage-visual-basic"></a><span data-ttu-id="d5e0e-102">/codepage(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5e0e-102">/codepage (Visual Basic)</span></span>
<span data-ttu-id="d5e0e-103">컴파일할 때 모든 소스 코드 파일에 사용할 코드 페이지를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-103">Specifies the code page to use for all source-code files in the compilation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e0e-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5e0e-104">Syntax</span></span>  
  
```  
/codepage:id  
```  
  
## <a name="arguments"></a><span data-ttu-id="d5e0e-105">인수</span><span class="sxs-lookup"><span data-stu-id="d5e0e-105">Arguments</span></span>  
  
|<span data-ttu-id="d5e0e-106">용어</span><span class="sxs-lookup"><span data-stu-id="d5e0e-106">Term</span></span>|<span data-ttu-id="d5e0e-107">정의</span><span class="sxs-lookup"><span data-stu-id="d5e0e-107">Definition</span></span>|  
|---|---|  
|`id`|<span data-ttu-id="d5e0e-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-108">Required.</span></span> <span data-ttu-id="d5e0e-109">컴파일러에서 지정한 코드 페이지를 사용 하 여 `id` 소스 파일의 인코딩을 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-109">The compiler uses the code page specified by `id` to interpret the encoding of the source files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5e0e-110">주의</span><span class="sxs-lookup"><span data-stu-id="d5e0e-110">Remarks</span></span>  
 <span data-ttu-id="d5e0e-111">특정 인코딩으로 저장 된 소스 코드를 컴파일하려면를 사용할 수 있습니다 `/codepage` 코드 페이지를 사용할지를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-111">To compile source code saved with a specific encoding, you can use `/codepage` to specify which code page should be used.</span></span> <span data-ttu-id="d5e0e-112">`/codepage` 옵션 컴파일에 모든 소스 코드 파일에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-112">The `/codepage` option applies to all source-code files in your compilation.</span></span> <span data-ttu-id="d5e0e-113">자세한 내용은 참조 [.NET Framework의 문자 인코딩을](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9)합니다.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-113">For more information, see [Character Encoding in the .NET Framework](http://msdn.microsoft.com/library/bf6d9823-4c2d-48af-b280-919c5af66ae9).</span></span>  
  
 <span data-ttu-id="d5e0e-114">`/codepage` 옵션에는 소스 코드 파일의 현재 ANSI 코드 페이지, 유니코드 또는 u t F-8을 사용 하 여 서명을 사용 하 여 저장 한 경우에 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-114">The `/codepage` option is not needed if the source-code files were saved using the current ANSI code page, Unicode, or UTF-8 with a signature.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="d5e0e-115">사용자에서 다른 인코딩을 지정 하지 않으면 기본적으로 모든 소스 코드 파일의 현재 ANSI 코드 페이지와 저장 된 **인코딩** 대화 상자입니다.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-115"> saves all source-code files with the current ANSI code page by default, unless the user specifies another encoding in the **Encoding** dialog box.</span></span> [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)]<span data-ttu-id="d5e0e-116">사용 하는 **인코딩** 대화 상자를 다른 코드 페이지와 함께 저장 하는 소스 코드 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-116"> uses the **Encoding** dialog box to open source-code files saved with a different code page.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5e0e-117">`/codepage` 옵션 내에서 사용할 수 없는 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] 개발 환경, 명령줄에서 컴파일할 때에 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5e0e-117">The `/codepage` option is not available from within the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e0e-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5e0e-118">See Also</span></span>  
 [<span data-ttu-id="d5e0e-119">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="d5e0e-119">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
