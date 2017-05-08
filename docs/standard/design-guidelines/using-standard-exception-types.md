---
title: "표준 예외 형식 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "표준 형식 예외를 throw합니다."
  - "예외 catch"
  - "예외를 catch"
  - "예외를 throw"
ms.assetid: ab22ce03-78f9-4dca-8824-c7ed3bdccc27
caps.latest.revision: 17
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 17
---
# 표준 예외 형식 사용
이 섹션에서는 자신의 사용량의 세부 정보 및 프레임 워크에서 제공 하는 표준 예외를 설명 합니다. 이 목록은 철저 한 있지는 않습니다. 다른 프레임 워크 예외 형식의 사용에 대 한.NET Framework 참조 설명서를 참조 하십시오.  
  
## 예외 및 SystemException  
 **X 하지 않으려면** throw <xref:System.Exception?displayProperty=fullName> 또는 <xref:System.SystemException?displayProperty=fullName>합니다.  
  
 **X 하지 않으려면** catch `System.Exception` 또는 `System.SystemException` 프레임 워크 코드에 다시 throw 하려는 경우가 아니면 합니다.  
  
 **X 방지** 포착 `System.Exception` 또는 `System.SystemException`, 최상위 예외 처리기를 제외 하 고 있습니다.  
  
## ApplicationException  
 **X 하지 않으려면** throw 하거나이 로부터 파생할 <xref:System.ApplicationException>합니다.  
  
## InvalidOperationException  
 **✓ 수행** throw는 <xref:System.InvalidOperationException> 개체가 부적절 한 상태입니다.  
  
## ArgumentException, ArgumentNullException을 및 ArgumentOutOfRangeException  
 **✓ 수행** throw <xref:System.ArgumentException> 또는 멤버에 잘못 된 인수가 전달 되 면 하위 형식 중 하나입니다. 해당 하는 경우 가장 많이 파생 된 예외 형식을 더 선호 합니다.  
  
 **✓ 수행** 설정의 `ParamName` 속성의 서브 클래스 중 하나를 throw 할 때 `ArgumentException`합니다.  
  
 이 속성은 throw 된 예외를 발생 시킨 매개 변수의 이름을 나타냅니다. 생성자 오버 로드 중 하나를 사용 하 여 속성을 설정할 수 있는 참고 합니다.  
  
 **✓ 수행** 사용 `value` 속성 setter의 암시적 값 매개 변수 이름에 대 한 합니다.  
  
## Nullreferenceexception이 발생, IndexOutOfRangeException 및 AccessViolationException  
 **X 하지 않으려면** 명시적 또는 암시적으로 throw 할 Api를 공개적으로 호출할 수 있도록 <xref:System.NullReferenceException>, 를<xref:System.AccessViolationException>, 를 또는 <xref:System.IndexOutOfRangeException>합니다. 이러한 예외 예약 된 페이지와 실행 엔진에 의해 throw 및 대부분의 경우 버그를 나타냅니다.  
  
 인수 이러한 예외를 throw 되지 않도록 하려면 검사를 수행 합니다. 시간이 지남에 따라 변경 될 수 있는 방법의 구현 세부 정보를 노출 이러한 예외를 throw 합니다.  
  
## StackOverflowException  
 **X 하지 않으려면** 명시적으로 throw <xref:System.StackOverflowException>합니다. 예외는 CLR에서만 명시적으로 throw 되어야 합니다.  
  
 **X 하지 않으려면** catch `StackOverflowException`합니다.  
  
 임의의 스택 오버플로 경우에도 일관성을 유지 하는 관리 되는 코드를 작성할 거의 불가능 합니다. CLR의 관리 되지 않는 부분에서 임의의 스택 오버플로 철회 하는 대신 스택이 잘 정의 된 위치로 이동 하는 프로브를 사용 하 여 일관성을 유지 합니다.  
  
## OutOfMemoryException  
 **X 하지 않으려면** 명시적으로 throw <xref:System.OutOfMemoryException>합니다. 이 예외만 CLR 인프라에 의해 throw 되는 것입니다.  
  
## ComException, SEHException, 및 ExecutionEngineException  
 **X 하지 않으려면** 명시적으로 throw <xref:System.Runtime.InteropServices.COMException>,  <xref:System.ExecutionEngineException>, 및 <xref:System.Runtime.InteropServices.SEHException>합니다. 이러한 예외만 CLR 인프라에 의해 throw 되는 것입니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [예외에 대 한 디자인 지침](../../../docs/standard/design-guidelines/exceptions.md)