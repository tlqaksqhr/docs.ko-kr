---
title: 필드 디자인
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d47934c3fed17f75a97ef5da0397c6ceba53d68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571119"
---
# <a name="field-design"></a>필드 디자인
캡슐화의 원칙 개체 지향 디자인에서 가장 중요 한 개념 중 하나를입니다. 이 규칙에 따르면 개체 내부에 저장 된 데이터를 해당 개체에만 액세스할 수 여야 합니다.  
  
 원칙을 해석 하는 유용한 방법은 말 (이름 또는 형식 변경) 해당 형식의 필드에 변경할 수는 형식의 멤버에 대 한 외의 다른 코드를 중단시 키 지 않고도 있도록 형식에 디자인 해야 하는 합니다. 이 해석을 즉시 모든 필드를 private 여야 하며 의미 합니다.  
  
 이러한 필드 정의 따라 거의 필요가 없으며 변경 때문에이 엄격한 제한에서 상수 및 정적 읽기 전용 필드를 제외 합니다.  
  
 **X DO NOT** 공용 또는 보호 되는 인스턴스 필드를 제공 합니다.  
  
 Public 또는 protected 하는 대신 필드에 액세스 하기 위한 속성을 제공 해야 합니다.  
  
 **✓ DO** 상수 필드는 변경 되지 않는 상수를 사용 합니다.  
  
 컴파일러는 호출 코드에 직접 const 필드의 값을 굽습니다. 따라서 const 값 호환성 손상 위험 없이 변경할 수 없습니다.  
  
 **✓ DO** 공용 정적을 사용 하 여 `readonly` 미리 정의 된 개체 인스턴스에 대 한 필드입니다.  
  
 미리 정의 된 형식 인스턴스의 경우 public으로 읽기 전용 정적 필드 형식 자체의 선언입니다.  
  
 **X DO NOT** 변경할 수 있는 형식의 인스턴스를 할당할 `readonly` 필드입니다.  
  
 변경 가능한 형식은 인스턴스화되는 후 수정할 수 있는 인스턴스는 형식이입니다. 예를 들어, 배열, 대부분의 컬렉션 및 스트림 모두 변경할 수 있는 유형 하지만 <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, 및 <xref:System.String?displayProperty=nameWithType> 는 모두 변경할 수 없습니다. 대체 되 고 있는 필드에 저장 된 인스턴스는 참조 형식 필드는 읽기 전용 한정자 없지만 필드의 인스턴스 데이터는 인스턴스 변경 멤버를 호출 하 여 수정 하지 못하도록 방지 되지 않습니다.  
  
 *Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*  
  
 *피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*  
  
## <a name="see-also"></a>참고 항목  
 [멤버 디자인 지침](../../../docs/standard/design-guidelines/member.md)  
 [프레임워크 디자인 지침](../../../docs/standard/design-guidelines/index.md)
