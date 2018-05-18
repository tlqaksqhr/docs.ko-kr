---
title: Exception 클래스 및 속성
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- exceptions, Exception class
- Exception class
ms.assetid: e2e1f8c4-e7b4-467d-9a66-13c90861221d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9cdc464234871fc07feeeb8dd02635ebdd151d76
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="exception-class-and-properties"></a>Exception 클래스 및 속성

<xref:System.Exception> 클래스는 예외가 상속받는 기본 클래스입니다. 예를 들어 <xref:System.InvalidCastException> 클래스 계층 구조는 다음과 같습니다.

```
Object
  Exception
    SystemException
       InvalidCastException
```

<xref:System.Exception> 클래스에는 예외를 보다 쉽게 이해할 수 있도록 하는 다음 속성이 있습니다.

| 속성 이름 | 설명 |
| ------------- | ----------- |
| <xref:System.Exception.Data> | 키-값 쌍의 임의의 데이터를 보유하는 <xref:System.Collections.IDictionary>. |
| <xref:System.Exception.HelpLink> | 예외의 원인에 대한 광범위한 정보를 제공하는 도움말 파일의 URL(또는 URN)을 포함할 수 있습니다. |
| <xref:System.Exception.InnerException> | 이 속성을 사용하여 예외 처리 중 일련의 예외를 만들고 유지할 수 있습니다. 이전에 catch된 예외를 포함하는 새 예외를 만드는 데 사용할 수 있습니다. <xref:System.Exception.InnerException> 속성의 두 번째 예외에서 원래 예외를 캡처하고 두 번째 예외를 처리하는 코드에서 추가 정보를 검사하도록 허용할 수 있습니다. 예를 들어 부적절한 형식의 인수를 받는 메서드가 있다고 가정해봅시다.  코드에서 인수를 읽으려고 하지만 예외가 throw됩니다. 메서드가 예외를 catch하고 <xref:System.FormatException>을 throw합니다. 예외가 throw된 이유를 확인하는 호출자 기능을 개선하기 위해 때로는 메서드가 도우미 루틴에서 throw된 예외를 catch한 다음 발생한 오류를 자세히 나타내는 예외를 throw하는 것이 좋습니다. 보다 의미 있는 새 예외를 만들 수 있으며, 이 경우 내부 예외 참조를 원래 예외로 설정할 수 있습니다. 그런 다음 보다 의미 있는 이 예외를 호출자에게 throw할 수 있습니다. 이 기능을 사용하면 처음 throw된 예외로 끝나는 일련의 연결된 예외를 만들 수 있습니다. |
| <xref:System.Exception.Message> | 예외 원인에 대한 정보를 제공합니다.
| <xref:System.Exception.Source> | 오류를 발생시키는 응용 프로그램 또는 개체의 이름을 가져오거나 설정합니다. |
| <xref:System.Exception.StackTrace>| 오류가 발생한 위치를 확인하는 데 사용할 수 있는 스택 추적을 포함합니다. 디버깅 정보를 사용할 수 있는 경우 스택 추적에는 소스 파일 이름과 프로그램 줄 번호가 포함됩니다. |

<xref:System.Exception>에서 상속받는 대부분의 클래스는 추가 멤버를 구현하거나 추가 기능을 제공하지 않습니다. 단순히 <xref:System.Exception>에서 상속받습니다. 따라서 가장 중요한 예외 정보는 예외 클래스, 예외 이름 및 예외에 포함된 정보의 계층 구조에서 확인할 수 있습니다.

<xref:System.Exception>에서 파생된 개체만 throw 및 catch하는 것이 좋지만 <xref:System.Object> 클래스에서 파생된 모든 개체를 예외로 throw할 수 있습니다. 일부 언어는 <xref:System.Exception>에서 파생되지 않은 개체의 throw 및 catch를 지원하지 않습니다.
  
## <a name="see-also"></a>참고 항목  
[예외](index.md)
