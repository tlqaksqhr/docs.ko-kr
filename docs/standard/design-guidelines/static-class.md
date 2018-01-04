---
title: "정적 클래스 디자인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- type design guidelines, static classes
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], static
- static classes [.NET Framework]
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d67c14d8-c4dd-443f-affb-4ccae677c9b6
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8c36bf5790d033eddb6bb7e0d910482143a9bcac
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="static-class-design"></a><span data-ttu-id="d5dee-102">정적 클래스 디자인</span><span class="sxs-lookup"><span data-stu-id="d5dee-102">Static Class Design</span></span>
<span data-ttu-id="d5dee-103">정적 클래스는 정적 멤버만 포함 하는 클래스로 정의 됩니다 (에서 상속 되며, 인스턴스 멤버 외에도 물론 <xref:System.Object?displayProperty=nameWithType> 및 private 생성자를 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="d5dee-103">A static class is defined as a class that contains only static members (of course besides the instance members inherited from <xref:System.Object?displayProperty=nameWithType> and possibly a private constructor).</span></span> <span data-ttu-id="d5dee-104">일부 언어 정적 클래스에 대 한 기본 제공 지원을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d5dee-104">Some languages provide built-in support for static classes.</span></span> <span data-ttu-id="d5dee-105">C# 2.0 이상에서는 static으로 선언 된 클래스는 sealed, abstract, 응용 프로그램과 없는 인스턴스 멤버를 재정의 하거나 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5dee-105">In C# 2.0 and later, when a class is declared to be static, it is sealed, abstract, and no instance members can be overridden or declared.</span></span>  
  
 <span data-ttu-id="d5dee-106">정적 클래스는 순수 개체 지향 디자인과 단순성 간 절충안입니다.</span><span class="sxs-lookup"><span data-stu-id="d5dee-106">Static classes are a compromise between pure object-oriented design and simplicity.</span></span> <span data-ttu-id="d5dee-107">일반적으로 다른 작업에 대 한 바로 가기를 제공에 사용 되 (같은 <xref:System.IO.File?displayProperty=nameWithType>), 확장 메서드 또는 기능을 완전 한 개체 지향 래퍼는 릴리스됩니다의 소유자 (같은 <xref:System.Environment?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="d5dee-107">They are commonly used to provide shortcuts to other operations (such as <xref:System.IO.File?displayProperty=nameWithType>), holders of extension methods, or functionality for which a full object-oriented wrapper is unwarranted (such as <xref:System.Environment?displayProperty=nameWithType>).</span></span>  
  
 <span data-ttu-id="d5dee-108">**✓ 않습니다** 가급적 정적 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5dee-108">**✓ DO** use static classes sparingly.</span></span>  
  
 <span data-ttu-id="d5dee-109">정적 클래스는 개체 지향 프레임 워크의 핵심에 대 한 지원 되는 클래스 으로만 사용할 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5dee-109">Static classes should be used only as supporting classes for the object-oriented core of the framework.</span></span>  
  
 <span data-ttu-id="d5dee-110">**X 하지 않으면** 정적 클래스를 기타 버킷으로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5dee-110">**X DO NOT** treat static classes as a miscellaneous bucket.</span></span>  
  
 <span data-ttu-id="d5dee-111">**X 하지 않으면** 선언 또는 정적 클래스에 인스턴스 멤버를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5dee-111">**X DO NOT** declare or override instance members in static classes.</span></span>  
  
 <span data-ttu-id="d5dee-112">**✓ 않습니다** 봉인, 추상으로 정적 클래스를 선언 하 고 선택한 프로그래밍 언어에 정적 클래스에 대 한 기본 제공 지원 없는 경우 전용 인스턴스 생성자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5dee-112">**✓ DO** declare static classes as sealed, abstract, and add a private instance constructor if your programming language does not have built-in support for static classes.</span></span>  
  
 <span data-ttu-id="d5dee-113">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="d5dee-113">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d5dee-114">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="d5dee-114">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5dee-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5dee-115">See Also</span></span>  
 [<span data-ttu-id="d5dee-116">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d5dee-116">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="d5dee-117">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d5dee-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
