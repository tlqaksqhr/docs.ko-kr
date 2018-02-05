---
title: "방법: 표준.NET 개체를 직렬화 가능 인지 확인"
description: "런타임 시.NET 표준 형식이 serialize 될 수 있는지 여부를 결정 하는 방법을 보여 줍니다."
ms.custom: 
ms.date: 10/20/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8246e825202b3eb02db5d11f1fe55b4a0d14a4ea
ms.sourcegitcommit: 099aa20d9b6450d1b7452d782a55771a6ad8ff35
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2018
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a>방법: 표준.NET 개체를 직렬화 가능 인지 확인

.NET 표준 형식 및 해당 버전의 표준에 맞는 특정.NET 구현에 제공 되어야 하는 멤버를 정의 하는 사양입니다. 그러나.NET 표준을 정의 하지 않습니다는 형식이 직렬화 가능 인지 합니다. .NET 표준 라이브러리에 정의 된 형식으로 표시 되지 않은 <xref:System.SerializableAttribute> 특성입니다. 대신,.NET Framework 및.NET Core와 같은 특정.NET 구현이 특정 형식이 직렬화 가능 인지를 확인 하려면. 

사용자가 작성 한 라이브러리를 대상으로 하는.NET Standard, 하는 경우를 지 원하는.NET 표준.NET 구현 하 여 라이브러리를 사용할 수 있습니다. 즉, 있는지 알 수는 없습니다 사전에 특정 형식이 직렬화 가능; 인지 만 인지 직렬화 가능 실행 시 확인할 수 있습니다.

개체의 값을 검색 하 여 런타임 시 직렬화 가능 인지를 확인할 수 있습니다는 <xref:System.Type.IsSerializable> 의 속성을 <xref:System.Type> 해당 개체의 형식을 나타내는 개체입니다. 다음 예제에는 하나의 구현을 제공합니다. 정의 `IsSerializable(Object)` 확장 메서드를 나타내는 있는지 여부를 <xref:System.Object> 인스턴스를 serialize 할 수 있습니다.

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

모든 개체를 확인 하는지 여부를 것 수 직렬화 및 역직렬화 될 경우 현재.NET 구현에 다음 예제와 같이 메서드에 전달할 수 있습니다.

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a>참고 항목

[이진 serialization](binary-serialization.md)   
<xref:System.SerializableAttribute?displayProperty=nameWithType>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
