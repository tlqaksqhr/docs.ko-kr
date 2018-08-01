---
title: 사용 지침
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02905c193387f78430ce1885449055060d07bf82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571035"
---
# <a name="usage-guidelines"></a><span data-ttu-id="d5a99-102">사용 지침</span><span class="sxs-lookup"><span data-stu-id="d5a99-102">Usage Guidelines</span></span>
<span data-ttu-id="d5a99-103">이 섹션에는 공개적으로 액세스할 수 있는 Api에서 공용 형식 사용에 대 한 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5a99-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="d5a99-104">기본 제공 프레임 워크 형식 (예: 직렬화 특성) 및 일반 연산자 오버 로딩을 직접 사용을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="d5a99-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>  
  
 <span data-ttu-id="d5a99-105"><xref:System.IDisposable?displayProperty=nameWithType> 인터페이스가이 섹션에서는 적용 되지 않는 있지만에 대해서는 설명의 [Dispose 패턴](../../../docs/standard/design-guidelines/dispose-pattern.md) 섹션.</span><span class="sxs-lookup"><span data-stu-id="d5a99-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d5a99-106">지침 및 다른 일반적인 방법에 대 한 추가 정보에 대 한.NET Framework의 기본 제공 형식 참조 다음에 대 한 참조 항목: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType> , <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d5a99-106">For guidelines and additional information about about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5a99-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d5a99-107">In This Section</span></span>  
 [<span data-ttu-id="d5a99-108">배열</span><span class="sxs-lookup"><span data-stu-id="d5a99-108">Arrays</span></span>](../../../docs/standard/design-guidelines/arrays.md)  
 [<span data-ttu-id="d5a99-109">특성</span><span class="sxs-lookup"><span data-stu-id="d5a99-109">Attributes</span></span>](../../../docs/standard/design-guidelines/attributes.md)  
 [<span data-ttu-id="d5a99-110">컬렉션</span><span class="sxs-lookup"><span data-stu-id="d5a99-110">Collections</span></span>](/cpp/mfc/collections)  
 [<span data-ttu-id="d5a99-111">serialization</span><span class="sxs-lookup"><span data-stu-id="d5a99-111">Serialization</span></span>](../../../docs/standard/design-guidelines/serialization.md)  
 [<span data-ttu-id="d5a99-112">System.Xml 사용법</span><span class="sxs-lookup"><span data-stu-id="d5a99-112">System.Xml Usage</span></span>](../../../docs/standard/design-guidelines/system-xml-usage.md)  
 [<span data-ttu-id="d5a99-113">같음 연산자</span><span class="sxs-lookup"><span data-stu-id="d5a99-113">Equality Operators</span></span>](../../../docs/standard/design-guidelines/equality-operators.md)  
 <span data-ttu-id="d5a99-114">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="d5a99-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d5a99-115">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="d5a99-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5a99-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5a99-116">See Also</span></span>  
 [<span data-ttu-id="d5a99-117">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="d5a99-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
