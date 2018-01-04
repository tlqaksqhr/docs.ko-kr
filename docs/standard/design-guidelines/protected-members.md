---
title: "보호된 멤버"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- members [.NET Framework], protected
- protected members
- classes [.NET Framework], unsealed
- classes [.NET Framework], protected members
- unsealed classes
- customizing class behavior
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 03d9eac41e693568da2d057bc1394c426df4c736
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="protected-members"></a><span data-ttu-id="06532-102">보호된 멤버</span><span class="sxs-lookup"><span data-stu-id="06532-102">Protected Members</span></span>
<span data-ttu-id="06532-103">단독으로 보호 된 멤버는 확장성을 제공 하지 않습니다 하지만 더 강력한 서브클래싱을 통해 확장성을 내릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06532-103">Protected members by themselves do not provide any extensibility, but they can make extensibility through subclassing more powerful.</span></span> <span data-ttu-id="06532-104">기본 공용 인터페이스를 불필요 하 게 하므로 복잡해 집니다 하지 않고 고급 사용자 지정 옵션을 표시 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06532-104">They can be used to expose advanced customization options without unnecessarily complicating the main public interface.</span></span>  
  
 <span data-ttu-id="06532-105">프레임 워크 디자이너에 주의를 기울여야 보호 된 멤버 이름이 "보호" 보안에 대해 잘못 된 지정할 수 없기 때문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="06532-105">Framework designers need to be careful with protected members because the name "protected" can give a false sense of security.</span></span> <span data-ttu-id="06532-106">모든 사용자는 하위 클래스는 봉인 되지 않은 클래스 및 멤버에 보호 된 액세스를 하 하 고 공용 멤버에 사용 되는 코딩 관례 보호 된 멤버에 적용 되는 동일한 하므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="06532-106">Anyone is able to subclass an unsealed class and access protected members, and so all the same defensive coding practices used for public members apply to protected members.</span></span>  
  
 <span data-ttu-id="06532-107">**✓ 고려** 를 사용 하 여 고급 사용자 지정에 대 한 멤버를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="06532-107">**✓ CONSIDER** using protected members for advanced customization.</span></span>  
  
 <span data-ttu-id="06532-108">**✓ 않습니다** 보안, 설명서 및 호환성 분석용으로 public으로 봉인 되지 않은 클래스의 보호 된 멤버를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="06532-108">**✓ DO** treat protected members in unsealed classes as public for the purpose of security, documentation, and compatibility analysis.</span></span>  
  
 <span data-ttu-id="06532-109">누구 든 지 클래스에서 상속 하 고 보호 된 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06532-109">Anyone can inherit from a class and access the protected members.</span></span>  
  
 <span data-ttu-id="06532-110">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="06532-110">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="06532-111">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="06532-111">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06532-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06532-112">See Also</span></span>  
 [<span data-ttu-id="06532-113">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="06532-113">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="06532-114">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="06532-114">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
