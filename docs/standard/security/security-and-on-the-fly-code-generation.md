---
title: 보안 및 빠른 코드 생성
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- code security, on-the-fly code generation
- on-the-fly code generation
- security [.NET Framework], on-the-fly code generation
- secure coding, on-the-fly code generation
ms.assetid: 6d221724-bb21-4d76-90c3-0ee2a2e69be2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2cfc93e1c8d3d9e878d96de164b0d646e62c0998
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583970"
---
# <a name="security-and-on-the-fly-code-generation"></a><span data-ttu-id="a925e-102">보안 및 빠른 코드 생성</span><span class="sxs-lookup"><span data-stu-id="a925e-102">Security and On-the-Fly Code Generation</span></span>
<span data-ttu-id="a925e-103">일부 라이브러리는 코드를 생성하고 실행하여 호출자에 대한 일부 작업을 수행하는 방식으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a925e-103">Some libraries operate by generating code and running it to perform some operation for the caller.</span></span> <span data-ttu-id="a925e-104">기본적인 문제는 낮은 신뢰 수준의 코드를 대신하여 코드를 생성하고 높은 신뢰 수준에서 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a925e-104">The basic problem is generating code on behalf of lesser-trust code and running it at a higher trust.</span></span> <span data-ttu-id="a925e-105">호출자가 코드 생성에 영향을 줄 수 있는 경우 문제가 더욱 악화되므로 안전하다고 생각하는 코드만 생성되도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a925e-105">The problem worsens when the caller can influence code generation, so you must ensure that only code you consider safe is generated.</span></span>  
  
 <span data-ttu-id="a925e-106">항상 어떤 코드를 생성하는지 정확히 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a925e-106">You need to know exactly what code you are generating at all times.</span></span> <span data-ttu-id="a925e-107">즉, 따옴표로 묶인 문자열(예기치 않은 코드 요소를 포함할 수 없도록 이스케이프해야 함), 식별자(유효한 식별자인지 확인해야 함) 또는 기타 값인지에 관계없이 사용자로부터 얻는 값을 엄격하게 제어해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a925e-107">This means that you must have strict controls on any values that you get from a user, be they quote-enclosed strings (which should be escaped so they cannot include unexpected code elements), identifiers (which should be checked to verify that they are valid identifiers), or anything else.</span></span> <span data-ttu-id="a925e-108">보안 취약성인 경우는 드물지만 식별자에 이상한 문자가 포함되도록 컴파일된 어셈블리를 수정할 수 있고 이 경우 어셈블리가 손상되기 때문에 식별자는 위험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a925e-108">Identifiers can be dangerous because a compiled assembly can be modified so that its identifiers contain strange characters, which will probably break it (although this is rarely a security vulnerability).</span></span>  
  
 <span data-ttu-id="a925e-109">리플렉션 내보내기를 사용하여 코드를 생성하는 것이 좋으며, 그러면 이러한 많은 문제를 방지하는 데 도움이 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="a925e-109">It is recommended that you generate code with reflection emit, which often helps you avoid many of these problems.</span></span>  
  
 <span data-ttu-id="a925e-110">코드를 컴파일하는 경우 악성 프로그램이 코드를 수정할 수 있는 방법이 있는지 여부를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="a925e-110">When you compile the code, consider whether there is some way a malicious program could modify it.</span></span> <span data-ttu-id="a925e-111">컴파일러가 소스 코드를 읽기 전이나 코드가 .dll 파일을 로드하기 전에 악성 코드가 디스크의 소스 코드를 변경할 수 있는 짧은 기간이 있나요?</span><span class="sxs-lookup"><span data-stu-id="a925e-111">Is there a small window of time during which malicious code can change source code on disk before the compiler reads it or before your code loads the .dll file?</span></span> <span data-ttu-id="a925e-112">있다면 파일 시스템에서 액세스 제어 목록을 적절하게 사용하여 이러한 파일을 포함하는 디렉터리를 보호해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a925e-112">If so, you must protect the directory containing these files, using an Access Control List in the file system, as appropriate.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a925e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a925e-113">See Also</span></span>  
 [<span data-ttu-id="a925e-114">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="a925e-114">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
