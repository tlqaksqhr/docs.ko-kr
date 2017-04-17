---
title: "대/소문자 표기법 | Microsoft Docs"
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
  - "카멜식 대 / 소문자 구분 이름 [.NET Framework]"
  - "클래스 라이브러리 디자인 지침 [.NET Framework] 첫 글자를 대문자로"
  - "파스칼식 대 / 소문자 구분 이름 [.NET Framework]"
  - "대/소문자 구분, 대/소문자 표기법"
  - "이름 [.NET Framework] 첫 글자를 대문자로"
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 16
---
# 대/소문자 표기법
지침에는 간단한 방법 사용 하 여이 장 레이아웃을 만드는 경우, 형식, 멤버 및 매개 변수를 읽기 쉽게 만들기 식별자를 일관 되 게 적용 하는 경우.  
  
## 식별자에 대 한 대\/소문자 규칙  
 식별자에는 단어를 구분 하는 식별자의 각 단어의 첫 글자를 대문자로 합니다. 단어를 구분 하기 위해 밑줄을 사용 하지 않는 또는 식별자의 모든 위치에서 문제입니다. 두 가지가 적절 한 식별자의 사용에 따라 식별자를 활용 하시기 바랍니다.  
  
-   PascalCasing  
  
-   camelCasing  
  
 다음 예제와 같이 매개 변수 이름 제외한 모든 식별자에 사용 되는 PascalCasing 규칙에 \(머리 글자어 길이에서 두 글자를 통해\) 각 단어의 첫 번째 문자를 대문자로 표시:  
  
 `PropertyDescriptor`   
 `HtmlTag`  
  
 다음 식별자와 같이 두 문자로 머리글자어는 두 글자를 대문자로 작성에 대 한 특별 한 경우 구성 됩니다.  
  
 `IOStream`  
  
 다음 예제와 같이 매개 변수 이름에 대해서만 사용 되는 camelCasing 규칙에 첫 번째 단어를 제외한 각 단어의 첫 번째 문자를 대문자로 표시 합니다. 또한이 예에서는, 카멜식 대\/소문자를 사용 하는 식별자를 시작 하는 2 자 약어는 모두 소문자.  
  
 `propertyDescriptor`   
 `ioStream`   
 `htmlTag`  
  
 **✓ 수행** PascalCasing 여러 단어로 구성 된 모든 공용 멤버, 형식 및 네임 스페이스 이름을 사용 합니다.  
  
 **✓ 수행** camelCasing 매개 변수 이름에 사용 합니다.  
  
 다음 표에서 서로 다른 종류의 식별자에 대 한 대\/소문자 규칙을 설명합니다.  
  
|식별자|대\/소문자 구분|예제|  
|---------|---------------|--------|  
|네임스페이스|파스칼|`namespace System.Security { ... }`|  
|형식|파스칼|`public class StreamReader { ... }`|  
|인터페이스|파스칼|`public interface IEnumerable { ... }`|  
|메서드|파스칼|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|속성|파스칼|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|이벤트|파스칼|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|필드|파스칼|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|열거형 값|파스칼|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|매개 변수|카멜식 대\/소문자로|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## 복합 단어와 일반적인 용어를 대문자로  
 대부분 복합 용어는 단일 단어의 첫 글자를 대문자로 목적으로 처리 됩니다.  
  
 **X 하지 않으려면** 소위 닫힌 형식의 복합 단어 각 글자를 대문자로 표시 합니다.  
  
 이들은 끝점 등의 단일 word로 작성 된 복합 단어입니다. 대\/소문자 지침을 목적으로 단일 단어로 닫힌 형식의 복합 단어를 처리 합니다. 현재 사전의 사용 하 여 확인 복합 단어인 닫힌 형태로 기록 됩니다.  
  
|파스칼|카멜식 대\/소문자로|Not|  
|---------|-----------------|---------|  
|`BitFlag`|`bitFlag`|`Bitflag`|  
|`Callback`|`callback`|`CallBack`|  
|`Canceled`|`canceled`|`Cancelled`|  
|`DoNot`|`doNot`|`Don't`|  
|`Email`|`email`|`EMail`|  
|`Endpoint`|`endpoint`|`EndPoint`|  
|`FileName`|`fileName`|`Filename`|  
|`Gridline`|`gridline`|`GridLine`|  
|`Hashtable`|`hashtable`|`HashTable`|  
|`Id`|`id`|`ID`|  
|`Indexes`|`indexes`|`Indices`|  
|`LogOff`|`logOff`|`LogOut`|  
|`LogOn`|`logOn`|`LogIn`|  
|`Metadata`|`metadata`|`MetaData, metaData`|  
|`Multipanel`|`multipanel`|`MultiPanel`|  
|`Multiview`|`multiview`|`MultiView`|  
|`Namespace`|`namespace`|`NameSpace`|  
|`Ok`|`ok`|`OK`|  
|`Pi`|`pi`|`PI`|  
|`Placeholder`|`placeholder`|`PlaceHolder`|  
|`SignIn`|`signIn`|`SignOn`|  
|`SignOut`|`signOut`|`SignOff`|  
|`UserName`|`userName`|`Username`|  
|`WhiteSpace`|`whiteSpace`|`Whitespace`|  
|`Writable`|`writable`|`Writeable`|  
  
## 대\/소문자 구분  
 일부는 수행 하지만 CLR에서 실행할 수 있는 언어 대\/소문자 구분을 지원할 필요가 없습니다. 해당 언어에서 지 원하는 경우에 프레임 워크에 액세스할 수 있는 다른 언어는 그렇지 않습니다. 따라서 외부에서 액세스할 수 있는 모든 Api 경우 동일한 컨텍스트에서 두 이름을 구분 하는 단독으로 사용할 수 없습니다.  
  
 **X 하지 않으려면** 모든 프로그래밍 언어는 대 소문자를 구분 하는 것으로 가정 합니다. 하지 않습니다. 대\/소문자만 다른 이름 수 없습니다.  
  
 *부분 © 2005, 2009 Microsoft Corporation. All rights reserved.*  
  
 *피어슨 교육, i n c.에서의 사용 권한 때마다 다시 인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리, 제 2 판에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams Addison\-wesley Professional에서 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로 게시 합니다.*  
  
## 참고 항목  
 [프레임 워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)   
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)