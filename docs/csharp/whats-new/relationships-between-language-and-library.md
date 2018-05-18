---
title: 언어 기능 및 라이브러리 형식 간의 관계 | Microsoft Docs
description: 언어 기능은 종종 구현에 대한 라이브러리 형식에 의존합니다. 해당 관계를 이해합니다.
ms.date: 07/20/2017
ms.openlocfilehash: dfae7972af0a251a92700d7d33bd6f971eb1870e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="relationships-between-language-features-and-library-types"></a>언어 기능 및 라이브러리 형식 간의 관계

C# 언어 정의는 특정 형식 및 이러한 형식에서 액세스할 수 있는 특정 멤버를 갖는 표준 라이브러리를 필요로 합니다. 컴파일러는 다양한 많은 언어 기능에 이러한 필요한 이러한 형식과 멤버를 사용하는 코드를 생성합니다. 필요한 경우 해당 형식이나 멤버가 아직 배포되지 않은 환경에 대한 코드를 작성할 때 최신 버전의 언어에 필요한 형식을 포함하는 NuGet 패키지가 있습니다.

표준 라이브러리 기능에 대한 이 종속성은 첫 번째 버전부터 C# 언어의 일부였습니다. 해당 버전에서 예제가 포함되어 있습니다.

* <xref:System.Exception> - 모든 컴파일러 생성 예외에 사용됩니다.
* <xref:System.String> - C# `string` 형식은 <xref:System.String>의 동의어입니다.
* <xref:System.Int32> - `int`의 동의어입니다.

첫 번째 버전은 간단했습니다. 컴파일러 및 표준 라이브러리는 함께 제공되었고 각각 하나의 버전만 있었습니다.

후속 버전의 C#은 종속성에 가끔 새 형식 또는 멤버를 추가했습니다. 예를 들면 <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> 및 <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>입니다. C# 7.0은 <xref:System.ValueTuple>에 종속성을 추가하여 [튜플](../tuples.md) 언어 기능을 계속해서 구현합니다.

언어 디자인 팀은 호환 표준 라이브러리에 필요한 형식 및 멤버의 노출 영역을 최소화하려고 합니다. 해당 목표는 새 라이브러리 기능이 해당 언어로 원활하게 통합되는 단순한 디자인에 따라 조정됩니다. 표준 라이브러리에 새 형식 및 멤버를 필요로 하는 이후 버전의 C#에는 새 기능이 있을 예정입니다. 작업에서 해당 종속성을 관리하는 방법을 이해하는 것이 중요합니다.

## <a name="managing-your-dependencies"></a>종속성 관리

C# 컴파일러 도구는 이제 지원되는 플랫폼의 .NET 라이브러리의 릴리스 주기에서 분리됩니다. 사실상 서로 다른 .NET 라이브러리는 다른 릴리스 주기를 갖습니다. Windows에서 .NET Framework는 Windows 업데이트로 릴리스되고, .NET Core는 별도 일정으로 제공되며, Xamarin 버전의 라이브러리 업데이트는 각 대상 플랫폼에 대한 Xamarin 도구로 제공됩니다.

대부분의 시간에서 이러한 변경 내용이 발견되지 않습니다. 그러나 해당 플랫폼의 .NET 라이브러리에 아직 없는 기능을 필요로 하는 언어의 최신 버전을 사용하는 경우 이러한 새 유형을 제공하는 NuGet 패키지를 참조할 수 있습니다.
플랫폼으로서 앱 지원은 새 프레임워크를 설치로 업데이트되며 추가 참조를 제거할 수 있습니다.

이러한 분리는 해당 프레임워크가 없을 수도 있는 컴퓨터를 대상으로 하는 경우에도 새로운 언어 기능을 사용할 수 있음을 의미합니다.
