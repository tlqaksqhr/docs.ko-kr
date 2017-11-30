---
title: "표준.NET의 새로운 기능"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a>표준.NET의 새로운 기능

표준.NET은 해당 버전의 표준에 부합 하는.NET 구현에서 사용할 수 있어야 하는 Api 버전이 지정 된 집합이 정의 하는 형식 사양입니다. .NET 표준은 라이브러리 개발자에서 대상으로 지정됩니다. 표준의 해당 버전을 지 원하는 모든.NET Framework,.NET Core 또는 Xamarin 구현에는 표준.NET 버전을 대상으로 하는 라이브러리를 사용할 수 있습니다.

.NET 표준의 가장 최신 버전은 2.0입니다. 포함 된 Visual Studio 2017 버전 15.3 뿐 아니라.NET Core 2.0 SDK와 함께 설치 된.NET Core 작업의 합니다.

## <a name="supported-net-implementations"></a>지원 되는.NET 구현

.NET 표준 2.0은 다음과 같은.NET 구현에서 지원 됩니다.

- .NET core 2.0
- .NET Framework 4.6.1
- 모노 5.4
- Xamarin.iOS 10.14
- 3.8 Xamarin.Mac
- Xamarin.Android 8.0
- 유니버설 Windows 플랫폼 10.0.16299

## <a name="whats-new-in-the-net-standard-20"></a>표준.NET 2.0의 새로운 기능
 
.NET 표준 2.0에는 다음과 같은 새로운 기능이 포함 됩니다.

**Api 집합이 매우 확장 된**

버전 1.6 통해.NET 표준 포함 Api의 상대적으로 작은 하위 집합입니다. 제외 된.NET Framework 또는 Xamarin에 일반적으로 사용 된 많은 Api 했습니다. 이 인해 응용 프로그램 및 여러.NET 구현을 대상으로 하는 라이브러리를 개발 하는 경우 개발자가 익숙한 Api에 대 한 적합 한 대체 찾을 있도록 하므로 개발, 복잡 합니다. .NET 표준 2.0.NET 표준 1.6 이전 버전의 표준에서에서 사용할 수 있었던 것 보다 더 많은 Api 20, 000 개를 추가 하 여이 제한을 해결할 수 있습니다. 목록이.NET 표준 2.0에 추가 된 Api에 대 한 참조 [표준.NET 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md)합니다. 

일부 추가 기능에는 <xref:System> 표준.NET 2.0에서 네임 스페이스를 포함 합니다.

- 에 대 한 지원의 <xref:System.AppDomain> 클래스입니다.
- 추가 멤버에서 배열 작업에 대 한 지원 향상는 <xref:System.Array> 클래스입니다.
- 추가 멤버에서 특성 작업에 대 한 지원 향상는 <xref:System.Attribute> 클래스입니다.
- 더 잘 지원 및 추가 서식 옵션에 대 한 달력 <xref:System.DateTime> 값입니다.
- 추가 <xref:System.Decimal> 기능 반올림 합니다.
- 추가 기능에는 <xref:System.Environment> 클래스입니다.
- 통해 가비지 수집기에 대 한 제어 강화는 <xref:System.GC> 클래스입니다.
- 문자열 비교, 열거 및의 정규화에 대 한 지원 강화는 <xref:System.String> 클래스입니다.
- 일광 절약 조정 및에서 전환 시간에 대 한 지원의 <xref:System.TimeZoneInfo.AdjustmentRule> 및 <xref:System.TimeZoneInfo.TransitionTime> 클래스입니다.
- 기능을 크게 향상 된 <xref:System.Type> 클래스입니다.
- 사용 하는 예외 생성자를 추가 하 여 예외 개체의 deserialization에 대 한 지원 향상 <xref:System.Runtime.Serialization.SerializationInfo> 및 <xref:System.Runtime.Serialization.StreamingContext> 매개 변수입니다.

**.NET Framework 라이브러리에 대 한 지원**

라이브러리의 대다수는.NET Framework 보다는 표준.NET 대상으로 합니다. 그러나.NET 표준 2.0에 포함 된 Api에는 대부분 해당 라이브러리에 대 한 호출입니다. .NET 표준 2.0 부터는에서 액세스할 수 있습니다.NET Framework 라이브러리는 표준.NET 라이브러리를 사용 하 여 한 [호환성 shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification)합니다. 이 호환성 레이어 개발자;에 .NET Framework 라이브러리를 활용 하기 위해 어떤 작업도 수행할 필요가 없습니다.

단일입니다.NET Framework 클래스 라이브러리에서 호출 되는 Api는.NET 표준 2.0에 포함 되어야 합니다.

**Visual Basic에 대 한 지원**

이제 Visual basic에서.NET 표준 라이브러리를 개발할 수 있습니다. Visual Studio 2017 버전 15.3를 사용 하 여 Visual Basic 개발자 또는 설치 된.NET Core 작업과 나중에 Visual Studio에 이제.NET 표준 클래스 라이브러리 템플릿이 포함 됩니다. 다른 개발 도구 및 환경을 사용 하는 Visual Basic 개발자가 사용할 수 있습니다는 [새 dotnet](../../core/tools/dotnet-new.md) .NET 표준 라이브러리 프로젝트를 만들려면 명령입니다. 자세한 내용은 참조는 [도구.NET 표준 라이브러리에 대 한 지원](#tooling)합니다.

<a name="tooling" />**.NET 표준 라이브러리에 대 한 도구 지원**

.NET Core 2.0 및.NET 표준 2.0, 모두 Visual Studio 2017의 릴리스 및 [.NET Core 명령줄 인터페이스 (CLI)](../../core/tools/index.md) 표준.NET 라이브러리를 만들기 위한 지원 도구를 포함 합니다. 

Visual Studio를 설치 하는 경우는 **.NET Core 플랫폼 간 개발** 작업, 다음 그림 에서처럼 프로젝트 템플릿을 사용 하 여.NET 표준 2.0 라이브러리 프로젝트를 만들 수 있습니다. 

# <a name="ctabcsharp"></a>[C#](#tab/csharp)
![새.NET 표준 라이브러리 프로젝트에 추가](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[Visual Basic](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![새.NET 표준 라이브러리 프로젝트에 추가](./media/std-project-vb.png)
---

다음.NET Core CLI를 사용 하는 경우 [새 dotnet](../../core/tools/dotnet-new.md) 명령은 표준.NET 2.0을 대상으로 하는 클래스 라이브러리 프로젝트를 만듭니다.

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a>참고 항목
[.NET 표준](../net-standard.md)
[.NET 표준 소개](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
