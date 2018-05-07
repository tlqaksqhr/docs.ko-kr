---
title: '방법: 포함된 리소스에서 표준 시간대 복원'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31dd785c419d9a8e11eb23deabd2dfa71c4d6e9c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>방법: 포함된 리소스에서 표준 시간대 복원

이 항목에서는 리소스 파일에 저장 되어 있는 표준 시간대를 복원 하는 방법에 설명 합니다. 정보 및 표준 시간대 저장 하는 방법에 대 한 지침을 참조 하세요. [하는 방법: 포함 된 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)합니다.

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>포함된 리소스에서 TimeZoneInfo 개체를 deserialize 하기 위해

1. 사용자 지정 표준 시간대 표준 시간대를 검색할 수 없는 경우이 사용 하 여 인스턴스화하 려는 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드.

2. 인스턴스화하는 <xref:System.Resources.ResourceManager> 포함된 리소스 파일 및 리소스 파일을 포함 하는 어셈블리에 대 한 참조의 정규화 된 이름을 전달 하 여 개체입니다.

   포함된 리소스 파일의 정규화 된 이름을 확인할 수 없으면를 사용 하 여는 [Ildasm.exe (IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 어셈블리의 매니페스트를 검사할 수 있습니다. `.mresource` 항목은 리소스를 식별 합니다. 예제에서는 리소스의 정규화 된 이름이 `SerializeTimeZoneData.SerializedTimeZones`합니다.

   리소스 파일이 시간대 인스턴스화 코드를 포함 하는 동일한 어셈블리에 포함 되는 경우 호출 하 여에 대 한 참조를 검색할 수 있습니다는 `static` (`Shared` Visual basic에서) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> 메서드.

3. 경우에 대 한 호출에서 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드가 실패 하면 사용자 지정 표준 시간대를 인스턴스화할 경우 호출 하 여 serialize 된 표준 시간대를 포함 하는 문자열을 검색 하거나는 <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> 메서드.

4. 호출 하 여 표준 시간대 데이터를 deserialize는 <xref:System.TimeZoneInfo.FromSerializedString%2A> 메서드.

## <a name="example"></a>예제

다음 예제에서는 deserialize는 <xref:System.TimeZoneInfo> 포함된 된.NET XML 리소스 파일에 저장 된 개체입니다.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

이 코드 되도록 할 예외 처리를 보여 줍니다.는 <xref:System.TimeZoneInfo> 응용 프로그램에 필요한 개체는 있습니다. 인스턴스화하는 먼저 시도 <xref:System.TimeZoneInfo> 개체에서 사용 하 여 레지스트리 항목을 검색 하 여는 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드. 표준 시간대를 인스턴스화할 수 없는 경우 코드에서 포함된 리소스 파일에서 검색 합니다.

때문에 사용자 지정 표준 시간대에 대 한 데이터 (표준 시간대를 사용 하 여 인스턴스화할는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드) 저장 되지 않은 레지스트리에 코드 호출 하지 않습니다는 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> Palmer, 남극 대륙에 대 한 표준 시간대를 인스턴스화할 수입니다. 대신, 곧바로 호출 하기 전에 표준 시간대의 데이터를 포함 하는 문자열을 검색 하는 포함된 리소스 파일에는 <xref:System.TimeZoneInfo.FromSerializedString%2A> 메서드.

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* System.Windows.Forms.dll 및 System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.

* 다음 네임 스페이스 가져와야 합니다.

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>참고자료

[날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
[시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)
[하는 방법: 포함 된 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
