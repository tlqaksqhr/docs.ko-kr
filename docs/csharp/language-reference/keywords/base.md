---
title: "base(C# 참조) | Microsoft Docs"
description: base keyword (C#)
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "base"
  - "BaseClass.BaseClass"
  - "base_CSharpKeyword"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "base 키워드[C#]"
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 14
---
# base(C# 참조)
`base` 키워드는 다음과 같이 파생 클래스에서 기본 클래스의 멤버에 액세스하는 데 사용됩니다.  
  
-   다른 메서드로 재정의된 기본 클래스의 메서드를 호출합니다.  
  
-   파생 클래스의 인스턴스를 만들 때 호출해야 하는 기본 클래스 생성자를 지정합니다.  
  
 생성자, 인스턴스 메서드 또는 인스턴스 속성 접근자에서만 기본 클래스에 액세스할 수 있습니다.  
  
 정적 메서드 내에서는 `base` 키워드를 사용할 수 없습니다.  
  
 액세스한 기본 클래스는 클래스 선언에 지정된 기본 클래스입니다.  예를 들어 `class ClassB : ClassA`를 지정하면 ClassA의 기본 클래스에 상관 없이 ClassB에서 ClassA 멤버에 액세스합니다.  
  
## 예제  
 아래 예제에서 기본 클래스인 `Person`과 파생 클래스인 `Employee` 모두에 `Getinfo` 메서드가 있습니다.  `base` 키워드를 사용하면 파생 클래스에서 기본 클래스의 `Getinfo` 메서드를 호출할 수 있습니다.  
  
 [!code-cs[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/csharp/base_1.cs)]  
  
 다른 예제를 보려면 [new](../../../csharp/language-reference/keywords/new.md), [virtual](../../../csharp/language-reference/keywords/virtual.md) 및 [override](../../../csharp/language-reference/keywords/override.md)를 참조하십시오.  
  
## 예제  
 아래 예제에서는 파생 클래스의 인스턴스를 만들 때 기본 클래스 생성자를 지정하는 방법을 보여 줍니다.  
  
 [!code-cs[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/csharp/base_2.cs)]  
  
## C\# 언어 사양  
 [!INCLUDE[CSharplangspec](../../../csharp/language-reference/keywords/includes/csharplangspec-md.md)]  
  
## 참고 항목  
 [C\# 참조](../../../csharp/language-reference/index.md)   
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [C\# 키워드](../../../csharp/language-reference/keywords/index.md)   
 [this](../../../csharp/language-reference/keywords/this.md)