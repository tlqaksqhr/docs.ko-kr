---
title: 상태 데이터 보안
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- security [.NET Framework], state data
- code security, state data
- secure coding, state data
- state data security
ms.assetid: 12671309-2877-43fe-a3df-6863507e712d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe941fff7091fb579e41a3c417dbb2129bcf3e8c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33580785"
---
# <a name="securing-state-data"></a><span data-ttu-id="7f654-102">상태 데이터 보안</span><span class="sxs-lookup"><span data-stu-id="7f654-102">Securing State Data</span></span>
<span data-ttu-id="7f654-103">중요한 데이터를 처리하거나 보안 관련 사항을 결정해야 하는 응용 프로그램에서는 데이터를 자체적으로 제어해야 하며 악성 코드가 데이터에 직접 액세스하지 못하게 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f654-103">Applications that handle sensitive data or make any kind of security decisions need to keep that data under their own control and cannot allow other potentially malicious code to access the data directly.</span></span> <span data-ttu-id="7f654-104">데이터를 메모리에서 보호하는 최상의 방법은 데이터를 동일한 어셈블리로 제한된 범위 사용하여 private 또는 internal 변수로 선언하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7f654-104">The best way to protect data in memory is to declare the data as private or internal (with scope limited to the same assembly) variables.</span></span> <span data-ttu-id="7f654-105">그러나 이 데이터도 다음과 같이 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f654-105">However, even this data is subject to access you should be aware of:</span></span>  
  
-   <span data-ttu-id="7f654-106">리플렉션 메커니즘을 사용하면 개체를 참조할 수 있는 매우 신뢰되는 코드가 전용 멤버를 얻고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f654-106">Using reflection mechanisms, highly trusted code that can reference your object can get and set private members.</span></span>  
  
-   <span data-ttu-id="7f654-107">serialization을 사용하면 매우 신뢰되는 코드가 serialize된 형식의 개체에서 해당 데이터에 액세스할 수 있을 경우 효과적으로 전용 멤버를 얻고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f654-107">Using serialization, highly trusted code can effectively get and set private members if it can access the corresponding data in the serialized form of the object.</span></span>  
  
-   <span data-ttu-id="7f654-108">디버깅할 때 이 데이터를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f654-108">Under debugging, this data can be read.</span></span>  
  
 <span data-ttu-id="7f654-109">따라서 메서드나 속성이 실수로 해당 값을 노출하지 않도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f654-109">Make sure none of your own methods or properties exposes these values unintentionally.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f654-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f654-110">See Also</span></span>  
 [<span data-ttu-id="7f654-111">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="7f654-111">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
