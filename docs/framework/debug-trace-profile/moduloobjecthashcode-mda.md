---
title: "moduloObjectHashcode MDA | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "managed debugging assistants (MDAs), hashcode modulus"
  - "Modulo object hash code"
  - "moduloObjectHashcode MDA"
  - "hashcode modulus"
  - "MDAs (managed debugging assistants), hashcode modulus"
  - "GetHashCode method"
  - "modulus of hashcodes"
ms.assetid: b45366ff-2a7a-4b8e-ab01-537b72e9de68
caps.latest.revision: 10
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 10
---
# moduloObjectHashcode MDA
`moduloObjectHashcode` MDA\(관리 디버깅 도우미\)는 <xref:System.Object> 클래스의 동작을 변경하여 <xref:System.Object.GetHashCode%2A> 메서드에서 반환되는 해시 코드에서 modulo 연산을 수행합니다.  이 MDA의 기본 모듈러스는 <xref:System.Object.GetHashCode%2A>에서 모든 개체에 대해 0을 반환하도록 하는 1입니다.  
  
## 증상  
 CLR\(공용 언어 런타임\)의 새 버전으로 이동한 이후에 프로그램이 제대로 실행되지 않습니다.  
  
-   프로그램이 <xref:System.Collections.Hashtable>에서 잘못된 개체를 가져옵니다.  
  
-   <xref:System.Collections.Hashtable>의 열거형 순서가 변경되어 프로그램이 중단됩니다.  
  
-   같았던 두 개체가 더 이상 같지 않습니다.  
  
-   같지 않았던 두 개체가 이제 같습니다.  
  
## 원인  
 키에 대한 클래스의 <xref:System.Object.Equals%2A> 메서드를 <xref:System.Collections.Hashtable>로 구현하면 <xref:System.Object.GetHashCode%2A> 메서드에 대한 호출 결과를 비교하여 개체가 일치하는지 테스트하므로 프로그램이 <xref:System.Collections.Hashtable>로부터 잘못된 개체를 가져올 수 있습니다.  두 개체의 필드 값이 다르더라도 두 개체의 해시 코드가 같을 수 있으므로 개체의 일치를 테스트하는 데 해시 코드를 사용해서는 안 됩니다.  실제로는 드문 편이지만 해시 코드의 충돌이 발생할 수 있습니다.  이러한 충돌의 결과로 <xref:System.Collections.Hashtable>의 조회에서 서로 다른 두 키가 같게 나타나고 <xref:System.Collections.Hashtable>에서 잘못된 개체가 반환됩니다.  성능상의 이유로 <xref:System.Object.GetHashCode%2A>를 구현하면 런타임 버전 사이를 서로 변경할 수 있으므로 하나의 버전에서는 발생하지 않는 충돌이 이후의 버전에서 발생할 수 있습니다.  이 MDA를 사용하여 해시 코드가 충돌하는 경우 코드에 버그가 있는지 테스트합니다.  이 MDA를 사용하면 <xref:System.Object.GetHashCode%2A> 메서드가 0을 반환하므로 모든 해시 코드가 충돌합니다.  MDA를 사용하면 프로그램의 실행 속도가 느려집니다.  
  
 키 변경에 대한 해시 코드의 계산에 알고리즘이 사용되는 경우 <xref:System.Collections.Hashtable>의 열거형 순서가 런타임의 한 버전에서 다른 버전으로 변경될 수 있습니다.  프로그램이 해시 테이블의 키 또는 값의 열거형 순서에 대한 종속성을 가지는지 테스트하려면 이 MDA를 사용할 수 있습니다.  
  
## 해결  
 해시 코드를 개체 ID 대신 사용하지 마십시오.  해시 코드를 비교하지 않도록 <xref:System.Object.Equals%2A?displayProperty=fullName> 메서드의 재정의를 구현합니다.  
  
 해시 테이블의 키 또는 값의 열거형 순서에 대한 종속성을 만들지 마십시오.  
  
## 런타임 효과  
 이 MDA를 사용하면 응용 프로그램의 실행 속도가 느려집니다.  이 MDA는 반환될 해시 코드를 사용하여 대신 모듈러스로 나눈 나머지를 반환합니다.  
  
## Output  
 이 MDA의 출력은 없습니다.  
  
## Configuration  
 `modulus` 특성은 해시 코드에 사용할 모듈러스를 지정합니다.  기본값은 1입니다.  
  
```  
<mdaConfig>  
  <assistants>  
    <moduloObjectHashcode modulus="1" />  
  </assistants>  
</mdaConfig>  
```  
  
## 참고 항목  
 <xref:System.Object.GetHashCode%2A?displayProperty=fullName>   
 <xref:System.Object.Equals%2A?displayProperty=fullName>   
 [Diagnosing Errors with Managed Debugging Assistants](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)