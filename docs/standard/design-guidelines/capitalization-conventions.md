---
title: 대/소문자 표기법
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- camel-case names [.NET Framework]
- class library design guidelines [.NET Framework], capitalization
- Pascal-case names [.NET Framework]
- case sensitivity, capitalization conventions
- names [.NET Framework], capitalization
ms.assetid: 4c4ea526-9203-486f-b72d-29d61c5b3c6d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ef7913a2601c3a791cb028b4074ce37b9e9421b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="capitalization-conventions"></a>대/소문자 표기법
지침에 사용 하기 위한 간단한 방법이 장 레이아웃을 만드는 경우, 형식, 멤버 및 매개 변수를 읽기 쉽게에 대 한 확인 식별자를 일관 되 게 적용 될 때.  
  
## <a name="capitalization-rules-for-identifiers"></a>식별자에 대 한 대/소문자 규칙  
 식별자에는 단어를 구분 하려면 식별자의 각 단어의 첫 글자를 대문자로 바꿉니다. 단어를 구분 하기 위해 밑줄을 사용 하지 않는 또는 식별자에 해당 문제에 대 한 합니다. 식별자의 사용에 따라 식별자 활용할 적절 한 두 가지가 있습니다.  
  
-   PascalCasing  
  
-   camelCasing  
  
 다음 예제에 나와 있는 것 처럼 매개 변수 이름 제외 하 고 모든 식별자에 사용 하는 PascalCasing 규칙 (통해의 길이 문자 2 자 약어 포함)는 각 단어의 첫 번째 문자를 대문자로 표시:  
  
 `PropertyDescriptor`  
 `HtmlTag`  
  
 다음 식별자에 표시 된 대로 특수 한 경우 두 문자는 대문자 2 자 약어에 대 한 구성 됩니다.  
  
 `IOStream`  
  
 다음 예제에 나와 있는 것 처럼 매개 변수 이름에 대해서만 사용 되는 camelCasing 규칙에 첫 번째 단어를 제외한 각 단어의 첫 번째 문자를 대문자로 바꿉니다. 또한 예제와 같이 카멜식 대/소문자를 사용 하는 식별자를 시작 하는 2 자 약어는 모두 소문자입니다.  
  
 `propertyDescriptor`  
 `ioStream`  
 `htmlTag`  
  
 **✓ 않습니다** PascalCasing 여러 단어로 구성 된 모든 public 멤버, 형식 및 네임 스페이스 이름을 사용 합니다.  
  
 **✓ 않습니다** camelCasing 매개 변수 이름에 사용 합니다.  
  
 다음 표에서 다양 한 유형의 식별자에 대 한 대/소문자 규칙을 설명합니다.  
  
|식별자|대/소문자 구분|예제|  
|----------------|------------|-------------|  
|네임스페이스|파스칼|`namespace System.Security { ... }`|  
|형식|파스칼|`public class StreamReader { ... }`|  
|인터페이스|파스칼|`public interface IEnumerable { ... }`|  
|메서드|파스칼|`public class Object {` <br />  `public virtual string ToString();` <br /> `}`|  
|속성|파스칼|`public class String {` <br />  `public int Length { get; }` <br /> `}`|  
|이벤트(event)|파스칼|`public class Process {` <br />  `public event EventHandler Exited;` <br /> `}`|  
|필드|파스칼|`public class MessageQueue {` <br />  `public static readonly TimeSpan` <br /> `InfiniteTimeout;` <br /> `}` <br /> `public struct UInt32 {` <br />  `public const Min = 0;` <br /> `}`|  
|열거형 값|파스칼|`public enum FileMode {` <br />  `Append,` <br />  `...` <br /> `}`|  
|매개 변수|카멜식 대 /|`public class Convert {` <br />  `public static int ToInt32(string value);` <br /> `}`|  
  
## <a name="capitalizing-compound-words-and-common-terms"></a>복합 단어 및 일반적인 용어 수익 창출  
 대부분 복합 단어는 대/소문자의 목적을 위해 단어도 간주 됩니다.  
  
 **X 하지 않으면** 소위 닫힌 형식의 복합 단어 각 글자를 대문자로 표시 합니다.  
  
 이들은 끝점 같은 한 단어로 작성 하는 복합 단어입니다. 대/소문자 표기 지침이 목적으로 닫힌 형식의 복합 단어를 한 단어를 처리 합니다. 현재 사전의 사용 하 여 확인 복합 단어인 경우 닫힌 형태로 기록 됩니다.  
  
|파스칼|카멜식 대 /|not|  
|------------|-----------|---------|  
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
  
## <a name="case-sensitivity"></a>대/소문자 구분  
 일부 작업도 하지만 대/소문자 구분을 지원 하기 위해 CLR에서 실행할 수 있는 언어 않아도 됩니다. 해당 언어에서 지 원하는 경우에 프레임 워크에 액세스할 수 있는 다른 언어는 그렇지 않습니다. 따라서 외부에서 액세스할 수 있는 모든 Api는 동일한 컨텍스트에서 두 이름을 구별할 단독으로 사례에 사용할 수 없습니다.  
  
 **X 하지 않으면** 모든 프로그래밍 언어는 대/소문자 구분 하는 것으로 가정 합니다. 그러나 동일하지 않습니다. 대/소문자만 다른 이름 수 없습니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)  
 [명명 지침](../../../docs/standard/design-guidelines/naming-guidelines.md)
