---
title: "수집 가능한 어셈블리 동적 형식 생성"
description: 
ms.date: 08/29/2017
ms.prod: .net
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection, dynamic assembly
- assemblies, collectible
- collectible assemblies, retrieving
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c9a613f4cc13c3e4189a59ace2e05d01d1bcb4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="collectible-assemblies-for-dynamic-type-generation"></a>수집 가능한 어셈블리 동적 형식 생성

*수집 가능한 어셈블리* 언로드할 수는 만든 응용 프로그램 도메인을 언로드하지 않고 동적 어셈블리입니다. 수집 가능한 어셈블리 및 포함 된 형식 사용 되는 스레드와 관리 되지 않는 모든 메모리를 회수할 수 있습니다. 어셈블리 이름 등의 정보는 내부 테이블에서 제거 됩니다.

사용 하 여 언로드를 활성화 하려면는 <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType> 플래그 지정 하는 동적 어셈블리를 만들 때. 어셈블리는 임시로 (즉, 저장할 수 없습니다)에 설명 된 제한 사항이 적용 되며는 [수집 가능한 어셈블리에 대 한 제한](#restrictions-on-collectible-assemblies) 섹션. 공용 언어 런타임 (CLR) 어셈블리와 관련 된 모든 개체를 놓을 때 자동으로 수집 가능한 어셈블리를 언로드합니다. 수집 가능한 어셈블리는 다른 모든 측면에서 생성 및 다른 동적 어셈블리와 동일한 방식으로 사용 됩니다.

## <a name="lifetime-of-collectible-assemblies"></a>수집 가능한 어셈블리의 수명

수집 가능한 어셈블리의 수명은 이러한 형식에서 생성 된 개체와 포함 된 형식에 대 한 참조의 현재 상태에 따라 제어 됩니다. 다음 중 하나 이상의 공용 언어 런타임 어셈블리가 언로드되지 않습니다 (`T` 는 어셈블리에 정의 된 모든 형식): 

- `T`의 인스턴스입니다.

- 배열 인스턴스의 `T`합니다.
 
- 가진 제네릭 형식 인스턴스의 `T` 그 형식 인수 중 하나로 합니다. 제네릭 컬렉션 여기에 `T`해당 컬렉션이 비어 있는 경우에 합니다.

- 인스턴스 <xref:System.Type> 또는 <xref:System.Reflection.Emit.TypeBuilder> 나타내는 `T`합니다. 

   > [!IMPORTANT]
   > 어셈블리의 부분을 나타내는 모든 개체를 해제 해야 합니다. <xref:System.Reflection.Emit.ModuleBuilder> 정의 하는 `T` 에 대 한 참조 유지는 <xref:System.Reflection.Emit.TypeBuilder>, 및 <xref:System.Reflection.Emit.AssemblyBuilder> 개체에 대 한 참조를 보관는 <xref:System.Reflection.Emit.ModuleBuilder>이므로 이러한 개체에 대 한 참조를 해제 해야 합니다. 있어도 <xref:System.Reflection.Emit.LocalBuilder> 또는 <xref:System.Reflection.Emit.ILGenerator> 생성에 사용 되는 `T` 언로드가 이루어지지 않습니다.

- 에 대 한 정적 참조 `T` 다른 동적으로 정의 된 유형으로 `T1` 하는 코드를 실행 하 여 계속 연결할 수는 있습니다. 예를 들어 `T1` 에서 파생 될 수도 있습니다 `T`, 또는 `T` 의 메서드에서 매개 변수의 형식이 될 수 있습니다 `T1`합니다.
 
- A **ByRef** 속해 있는 정적 필드에 `T`합니다.

- A <xref:System.RuntimeTypeHandle>, <xref:System.RuntimeFieldHandle>, 또는 <xref:System.RuntimeMethodHandle> 참조 하는 `T` 또는의 구성 요소에 `T`합니다.

- 액세스에 직접 또는 직접 사용 될 수 있는 모든 리플렉션 개체의 인스턴스는 <xref:System.Type> 을 나타내는 개체 `T`합니다. 예를 들어는 <xref:System.Type> 개체에 대 한 `T` 가지 며 요소 형식이 배열 형식에서 얻을 수 `T`, 또는 가진 제네릭 형식을 `T` 형식 인수로 합니다. 

- 메서드 `M` 모든 스레드의 호출 스택에 있는 `M` 는 방법이 `T` 또는 어셈블리에 정의 된 모듈 수준 메서드.

- 어셈블리의 모듈에 정의 된 정적 메서드를 사용 하는 대리자입니다.

이 목록에서 한 항목에 대해 하나의 형식 또는 어셈블리에서 한 개의 메서드만 있는 런타임에서 어셈블리를 언로드할 수 없습니다.

> [!NOTE]
> 런타임은 실제로 언로드되지 않습니다 어셈블리 목록에서 모든 항목에 대 한 종료 자가 실행 될 때까지 합니다.

수명 추적을 위해 생성된 된 제네릭 형식을 같은 `List<int>` (C#에서) 또는 `List(Of Integer)` (Visual Basic)에서는 하 되에서 만들고 수집 가능한 어셈블리를 생성 된 것으로 간주 됩니다 어셈블리에서 정의 하는 원본이 포함 된 형식 정의 또는 그 형식 인수 중 하나의 정의 포함 하는 어셈블리에 있습니다. 사용 되는 정확한 어셈블리는 구현 세부 정보 및 변경 될 수,
 
## <a name="restrictions-on-collectible-assemblies"></a>수집 가능한 어셈블리에 대 한 제한

수집 가능한 어셈블리에는 다음 제한 사항이 적용 됩니다. 

- **정적 참조**   
  일반 동적 어셈블리의 형식 수집 가능한 어셈블리에 정의 된 형식에 정적 참조를 가질 수 없습니다. 예를 들어, 수집 가능한 어셈블리의 형식에서 상속 되는 일반 형식을 정의 하는 경우는 <xref:System.NotSupportedException> 예외가 throw 됩니다. 수집 가능한 어셈블리의 형식에에서 다른 수집 가능한 어셈블리의 형식에 정적 참조를 가질 수 있지만이 참조 하는 어셈블리의 수명에 참조 된 어셈블리의 수명으로 연장 합니다.

- **COM interop**   
   COM 인터페이스가 수집 가능한 어셈블리 내에서 정의할 수 있습니다 및 수집 가능한 어셈블리 내의 형식 인스턴스는 COM 개체로 변환 될 수 있습니다. 수집 가능한 어셈블리의 형식에에서 COM 호출 가능 래퍼 (CCW) 또는 런타임 호출 가능 래퍼 (RCW)으로 처리할 수 없습니다. 그러나 수집 가능한 어셈블리의 형식 COM 인터페이스를 구현 하는 개체를 사용할 수 있습니다.

- **플랫폼 호출**   
   포함 된 메서드는 <xref:System.Runtime.InteropServices.DllImportAttribute> 특성 수집 가능한 어셈블리에서 선언 될 때 컴파일되지 것입니다. <xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType> 명령 수집 가능한 어셈블리의 형식에에서 구현에서 사용할 수 없습니다 및 비관리 코드에 이러한 형식을 마샬링할 수 없습니다. 그러나 비 수집 가능한 어셈블리에 선언 된 진입점을 사용 하 여 네이티브 코드를 호출할 수 있습니다.
 
- **마샬링**   
   수집 가능한 어셈블리에 정의 됩니다 (특히 대리자)의 개체를 마샬링할 수 없습니다. 모든 임시 내보낸된 형식에 대 한 제한입니다.

- **어셈블리 로드**   
   리플렉션 내보내기는 수집 가능한 어셈블리 로드에 대해 지원 되는 유일한 메커니즘입니다. 다른 형태의 어셈블리 로드를 사용 하 여 로드 된 어셈블리를 언로드할 수 없습니다.
 
- **컨텍스트 바인딩된 개체**    
   상황에 맞는 정적 변수는 지원 되지 않습니다. 수집 가능한 어셈블리에서 형식을 확장할 수 없습니다 <xref:System.ContextBoundObject>합니다. 그러나 수집 가능한 어셈블리의 코드는 다른 곳에서 정의 된 컨텍스트 바인딩된 개체를 사용할 수 있습니다.

- **Thread 정적 데이터**       
   Thread 정적 변수는 지원 되지 않습니다.

## <a name="see-also"></a>참고 항목

[동적 메서드 및 어셈블리 내보내기](emitting-dynamic-methods-and-assemblies.md)
