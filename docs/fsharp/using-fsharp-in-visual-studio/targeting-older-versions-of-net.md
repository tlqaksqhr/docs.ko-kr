---
title: Windows 8에서 .NET Framework 2.0 대상 지정
description: 'F #을 사용 하는 경우에 이전 버전의.NET Framework를 대상으로 하는 방법을 알아봅니다.'
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 7c9bd8087da94a476105729b6f5b050fc66629a2
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="targeting-older-versions-of-net"></a>이전 버전의 .NET 대상 지정

> [!NOTE]
이 문서는 최신 Visual Studio와 함께 최신 상태로 되지 않습니다.  업데이트 됩니다.

3.0 또는 3.5 F #에서 Visual Studio Windows 8.1 설치 된 경우 프로젝트는.NET Framework 2.0 대상으로 하려는 경우 다음과 같은 오류가 나타날 수 있습니다. 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

이 오류 조건 중 다음과 같은 상황에서 발생할 것으로 알려져 있습니다.


- Windows 8.1 Visual Studio를 설치 합니다.
<br />

- Visual Studio를 설치 하기 전에.NET Framework 3.5를 사용 하도록 설정 하지 않았습니다.
<br />

- 프로젝트가는.NET Framework 2.0, 3.0 또는 3.5를 대상 으로합니다.
<br />

Visual Studio를 설치할 때 설치 된.NET Framework 버전을 검색 하 고.NET Framework 3.5 설치 되었고 사용 하는 경우에 F # Runtime 2.0을 설치 합니다.


## <a name="resolving-the-error"></a>오류 해결
이 오류를 해결 하려면 최신 버전의.NET Framework를 대상 중 하나를 할 수 있습니다 또는 Windows 8.1.NET Framework 3.5를 사용 하도록 설정 하 고 다음을 사용한 Visual Studio에 대 한 설치 프로그램을 실행 하 여 F # 2.0 런타임을 설치할 수 있습니다는 **복구** 옵션입니다.


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a>Windows 8.1.NET Framework 3.5를 사용 하도록 설정 하려면

1. 에 **시작** 화면에서 입력 하기 시작 **제어판**합니다.
<br />  해당 이름을 입력 하면는 **제어판** 아이콘 아래에 표시는 **앱** 제목입니다.
<br />

2. 선택 된 **제어판** 아이콘을 선택는 **프로그램** 아이콘을 선택한 후는 **Windows 기능 설정 또는 해제** 링크 합니다.
<br />

3. 다음 사항을 확인는 **.NET Framework 3.5 (.NET 2.0 및 3.0 포함)** 확인란을 선택한 다음 선택는 **확인** 단추입니다.
<br />  .NET Framework의 선택적 구성 요소에 대 한 모든 자식 노드에 대 한 확인란을 선택 하지 않아도 됩니다.
<br />  .NET Framework 3.5은 이미 되지 않은 경우에 사용할 수 있습니다.
<br />


#### <a name="to-install-the-f-20-runtime"></a>F # 2.0 런타임을 설치 하려면

1. 제어판에서 선택 된 **프로그램** 링크를 선택한 다음 선택는 **프로그램 및 기능** 링크 합니다.
<br />

2. 설치 된 프로그램 목록에서 설치 하 고 다음을 선택 하는 Visual Studio의 버전을 선택 된 **변경** 단추입니다.
<br />

3. 설치 프로그램이 시작 된 후 선택 된 **복구** 단추입니다.
<br />  자세한 내용은 참조 [Visual Studio 설치](https://msdn.microsoft.com/library/e2h7fzkw.aspx)합니다.
<br />
## <a name="see-also"></a>참고 항목
[Visual F#](../index.md)
