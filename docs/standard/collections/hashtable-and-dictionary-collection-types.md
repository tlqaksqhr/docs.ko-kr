---
title: "Hashtable 및 Dictionary 컬렉션 형식 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Hashtable class, grouping data in collections
- Hashtable collection type
- hash tables
- grouping data in collections, Hashtable collection type
- hash function
- collections [.NET Framework], Hashtable collection type
ms.assetid: bfc20837-3d02-4fc7-8a8f-c5215b6b7913
caps.latest.revision: 16
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 59aa4bd6160491ac6c6a4f45131531226ec7e58f
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="hashtable-and-dictionary-collection-types"></a>Hashtable 및 Dictionary 컬렉션 형식
<xref:System.Collections.Hashtable?displayProperty=fullName> 클래스와 <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> 및 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName> 제네릭 클래스는 <xref:System.Collections.IDictionary?displayProperty=fullName> 인터페이스를 구현합니다. <xref:System.Collections.Generic.Dictionary%602> 제네릭 클래스는 <xref:System.Collections.Generic.IDictionary%602> 제네릭 인터페이스도 구현합니다. 따라서 이러한 컬렉션의 각 요소는 한 쌍의 키-값입니다.  
  
 <xref:System.Collections.Hashtable> 개체는 컬렉션 요소를 포함하는 버킷으로 구성됩니다. 버킷은 <xref:System.Collections.Hashtable> 내 요소의 가상 하위 그룹으로, 대부분의 컬렉션보다 더 쉽고 빠르게 검색하고 가져올 수 있게 해줍니다. 각 버킷은 해시 함수를 사용하여 생성되고 요소의 키를 기반으로 하는 해시 코드와 연결됩니다.  
  
 제네릭 <xref:System.Collections.Generic.HashSet%601> 클래스는 고유 요소를 포함하기 위한 순서가 지정되지 않은 컬렉션입니다.  
  
 해시 함수는 키를 기준으로 숫자 해시 코드를 반환하는 알고리즘입니다. 키는 저장되는 개체의 일부 속성 값입니다. 해시 함수는 동일한 키에 대해 항상 동일한 해시 코드를 반환해야 합니다. 해시 함수는 두 개의 서로 다른 키에 대해 동일한 해시 코드를 생성할 수 있지만 각 고유 키에 대해 고유한 해시 코드를 생성하는 해시 함수를 통해 해시 테이블에서 요소를 검색할 때 성능이 더 낫습니다.  
  
 <xref:System.Collections.Hashtable>에서 요소로 사용되는 각 개체는 <xref:System.Object.GetHashCode%2A> 메서드 구현을 사용하여 자체 해시 코드를 생성할 수 있어야 합니다. 그러나 <xref:System.Collections.IHashCodeProvider> 구현을 매개 변수 중 하나로 사용하는 <xref:System.Collections.Hashtable> 생성자를 통해 <xref:System.Collections.Hashtable>의 모든 요소에 대한 해시 함수를 지정할 수도 있습니다.  
  
 개체가 <xref:System.Collections.Hashtable>에 추가된 경우 개체의 해시 코드와 일치하는 해시 코드와 연결된 버킷에 저장됩니다. <xref:System.Collections.Hashtable>에서 값을 검색하는 경우 해당 값에 대한 해시 코드가 생성되고 해당 해시 코드와 연결된 버킷이 검색됩니다.  
  
 예를 들어 문자열에 대한 해시 함수는 문자열에 포함된 각 문자의 ASCII 코드를 받은 다음 함께 결합하여 해시 코드를 생성합니다. 문자열 "picnic"은 문자열 "basket"의 해시 코드와 다른 해시 코드를 가지므로 문자열 "picnic"과 "basket"은 다른 버킷에 있습니다. 반면, "stressed"와 "desserts"는 동일한 해시 코드를 가지므로 동일한 버킷에 있습니다.  
  
 <xref:System.Collections.Generic.Dictionary%602> 및 <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 클래스는 <xref:System.Collections.Hashtable> 클래스와 기능이 동일합니다. 특정 형식(<xref:System.Object> 이외)의 <xref:System.Collections.Generic.Dictionary%602>는 값 형식의 <xref:System.Collections.Hashtable>보다 더 나은 성능을 제공합니다. 이는 <xref:System.Collections.Hashtable>의 요소가 <xref:System.Object> 형식이기 때문입니다. 따라서 boxing 및 unboxing은 일반적으로 값 형식을 저장하거나 검색할 때 발생합니다. <xref:System.Collections.Concurrent.ConcurrentDictionary%602> 클래스는 여러 스레드가 컬렉션에 동시에 액세스할 수 있는 경우에 사용해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Collections.Hashtable>   
 <xref:System.Collections.IDictionary>   
 <xref:System.Collections.IHashCodeProvider>   
 <xref:System.Collections.Generic.Dictionary%602>   
 <xref:System.Collections.Generic.IDictionary%602?displayProperty=fullName>   
 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=fullName>   
 [일반적으로 사용되는 컬렉션 형식](../../../docs/standard/collections/commonly-used-collection-types.md)
