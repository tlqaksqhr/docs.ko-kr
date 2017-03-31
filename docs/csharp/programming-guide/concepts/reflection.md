---
title: "리플렉션(C#) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: f80a2362-953b-4e8e-9759-cd5f334190d4
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ab40ab2258703670576084eccf7fd7e1b113d08d
ms.lasthandoff: 03/13/2017

---
# <a name="reflection-c"></a>리플렉션(C#)
리플렉션은 어셈블리, 모듈 및 형식을 설명하는 개체(<xref:System.Type> 형식)를 제공합니다. 리플렉션을 사용하면 동적으로 형식 인스턴스를 만들거나, 형식을 기존 개체에 바인딩하거나, 기존 개체에서 형식을 가져와 해당 메서드를 호출하거나, 필드 및 속성에 액세스할 수 있습니다. 코드에서 특성을 사용하는 경우 리플렉션은 특성에 대한 액세스를 제공합니다. 자세한 내용은 [특성](https://msdn.microsoft.com/library/5x6cd29c)을 참조하세요.  
  
 다음은 정적 메서드 `GetType`(`Object` 기본 클래스의 모든 형식에 상속됨)을 사용하여 변수 형식을 가져오는 간단한 리플렉션 예제입니다.  
  
```csharp  
// Using GetType to obtain type information:  
int i = 42;  
System.Type type = i.GetType();  
System.Console.WriteLine(type);  
```  
  
 출력은 다음과 같습니다.  
  
 `System.Int32`  
  
 다음 예제에서는 리플렉션을 사용하여 로드된 어셈블리의 전체 이름을 가져옵니다.  
  
```csharp  
// Using Reflection to get information from an Assembly:  
System.Reflection.Assembly info = typeof(System.Int32).Assembly;  
System.Console.WriteLine(info);  
```  
  
 출력은 다음과 같습니다.  
  
 `mscorlib, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`  
  
> [!NOTE]
>  C# 키워드 `protected` 및 `internal`은 IL에서 아무런 의미가 없으며 리플렉션 API에서 사용되지 않습니다. IL의 해당 용어는 *Family* 및 *Assembly*입니다. 리플렉션을 사용하여 `internal` 메서드를 식별하려면 <xref:System.Reflection.MethodBase.IsAssembly%2A> 속성을 사용하세요. `protected internal` 메서드를 식별하려면 <xref:System.Reflection.MethodBase.IsFamilyOrAssembly%2A>를 사용하세요.  
  
## <a name="reflection-overview"></a>리플렉션 개요  
 리플렉션은 다음과 같은 상황에서 유용합니다.  
  
-   프로그램 메타데이터의 특성에 액세스해야 하는 경우. 자세한 내용은 [특성에 저장된 정보 검색](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)을 참조하세요.  
  
-   어셈블리에서 형식을 검사하고 인스턴스화하려는 경우.  
  
-   런타임에 새 형식을 빌드하려는 경우. <xref:System.Reflection.Emit>의 클래스를 사용합니다.  
  
-   런타임에 바인딩을 수행하고 런타임에 생성된 형식의 메서드에 액세스하려는 경우. [동적으로 형식 로드 및 사용](http://msdn.microsoft.com/library/db985bec-5942-40ec-b13a-771ae98623dc) 항목을 참조하세요.  
  
## <a name="related-sections"></a>관련 단원  
 추가 정보  
  
-   [리플렉션](http://msdn.microsoft.com/library/d1a58e7f-fb39-4d50-bf84-e3b8f9bf9775)  
  
-   [형식 정보 보기](http://msdn.microsoft.com/library/7e7303a9-4064-4738-b4e7-b75974ed70d2)  
  
-   [리플렉션 및 제네릭 형식](http://msdn.microsoft.com/library/f7180fc5-dd41-42d4-8a8e-1b34288e06de)  
  
-   <xref:System.Reflection.Emit>  
  
-   [특성에 저장된 정보 검색](http://msdn.microsoft.com/library/37dfe4e3-7da0-48b6-a3d9-398981524e1c)  
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [공용 언어 런타임의 어셈블리](https://msdn.microsoft.com/library/k3677y81)
