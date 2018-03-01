---
title: ".NET Framework 클래스 라이브러리의 제네릭(C# 프로그래밍 가이드)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- generics [C#], in .NET Framework class library
ms.assetid: afdd5477-6770-4686-8297-f58a4d749daf
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 83ce8b8fe31a35e04c23c316ead5848aec79ec42
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="generics-in-the-net-framework-class-library-c-programming-guide"></a><span data-ttu-id="d6e1c-102">.NET Framework 클래스 라이브러리의 제네릭(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="d6e1c-102">Generics in the .NET Framework Class Library (C# Programming Guide)</span></span>
<span data-ttu-id="d6e1c-103">.NET Framework 클래스 라이브러리 버전 2.0은 바로 사용할 수 있는 여러 가지 제네릭 컬렉션 클래스 및 연결된 인터페이스가 포함된 새로운 네임스페이스 <xref:System.Collections.Generic>을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e1c-103">Version 2.0 of the .NET Framework class library provides a new namespace, <xref:System.Collections.Generic>, which includes several ready-to-use generic collection classes and associated interfaces.</span></span> <span data-ttu-id="d6e1c-104"><xref:System>과 같은 다른 네임스페이스는 <xref:System.IComparable%601>과 같은 새로운 제네릭 인터페이스도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e1c-104">Other namespaces, such as <xref:System>, also provide new generic interfaces such as <xref:System.IComparable%601>.</span></span> <span data-ttu-id="d6e1c-105">이러한 클래스 및 인터페이스는 .NET Framework의 이전 릴리스에서 제공된 제네릭이 아닌 컬렉션 클래스에 비해 보다 효율적이며 형식이 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e1c-105">These classes and interfaces are more efficient and type-safe than the non-generic collection classes provided in earlier releases of the .NET Framework.</span></span> <span data-ttu-id="d6e1c-106">사용자 지정 컬렉션 클래스를 디자인하고 구현하려면 먼저 .NET Framework 클래스 라이브러리에서 제공하는 클래스 중 하나에서 클래스를 사용하거나 파생시킬 수 있는지를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e1c-106">Before designing and implementing your own custom collection classes, consider whether you can use or derive a class from one of the classes provided in the .NET Framework class library.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e1c-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6e1c-107">See Also</span></span>  
 [<span data-ttu-id="d6e1c-108">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d6e1c-108">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d6e1c-109">제네릭 컬렉션 사용 기준</span><span class="sxs-lookup"><span data-stu-id="d6e1c-109">When to Use Generic Collections</span></span>](../../../standard/collections/when-to-use-generic-collections.md)  
 [<span data-ttu-id="d6e1c-110">컬렉션 및 데이터 구조</span><span class="sxs-lookup"><span data-stu-id="d6e1c-110">Collections and Data Structures</span></span>](../../../standard/collections/index.md)  
 [<span data-ttu-id="d6e1c-111">제네릭 소개</span><span class="sxs-lookup"><span data-stu-id="d6e1c-111">Introduction to Generics</span></span>](../../../csharp/programming-guide/generics/introduction-to-generics.md)
