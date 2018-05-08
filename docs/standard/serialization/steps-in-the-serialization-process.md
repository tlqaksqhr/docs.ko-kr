---
title: serialization 프로세스의 단계
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: b44b3b0539237c0f0d0a4af877e8955c6f612003
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="steps-in-the-serialization-process"></a>serialization 프로세스의 단계
<xref:System.Runtime.Serialization.Formatter.Serialize*> 메서드가 [포맷터](xref:System.Runtime.Serialization.Formatter)에서 호출되면 개체 serialization이 다음 규칙 시퀀스에 따라 진행됩니다.

- 포맷터에 서로게이트 선택기가 있는지 여부를 검사합니다. 포맷터에 서로게이트 선택기가 있는 경우에는 서로게이트 선택기가 지정된 형식의 개체를 처리하는지 검사합니다. 선택기가 개체 형식을 처리하는 경우에는 서로게이트 선택기에 대해 <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType>가 호출됩니다.

- 서로게이트 선택기가 없거나 개체 형식을 처리하지 않는 경우에는 개체가 [Serializable](xref:System.SerializableAttribute) 특성으로 표시되었는지 여부를 확인하는 검사가 수행됩니다. 개체가 해당 특성으로 표시되지 않은 경우 <xref:System.Runtime.Serialization.SerializationException>이 throw됩니다.

- 개체가 적절하게 표시된 경우에는 개체가 <xref:System.Runtime.Serialization.ISerializable> 인터페이스를 구현하는지 여부를 검사합니다. 이 인터페이스를 구현하는 경우에는 개체에 대해 <xref:System.Runtime.Serialization.ISerializable.GetObjectData*>가 호출됩니다.
  
- 개체가 <xref:System.Runtime.Serialization.ISerializable>을 구현하지 않는 경우에는 기본 serialization 정책이 사용되어 [NonSerialized](xref:System.NonSerializedAttribute)로 표시되지 않은 모든 필드를 serialize합니다.

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>참고 항목  
 [이진 serialization](binary-serialization.md)  
 [XML 및 SOAP serialization](xml-and-soap-serialization.md)