---
title: "방법: 설치 된.NET Framework 보안 업데이트 및 핫픽스를 결정 합니다."
description: "컴퓨터에 설치 된.NET Framework 보안 업데이트 및 핫픽스를 결정 하는 방법에 알아봅니다."
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- updates, determining for .NET Framework
- .NET Framework, determining updates
ms.assetid: 53c7b5f7-d47a-402a-b194-7244a696a88b
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c35705470a8e1b553eca2ca0c68d3b8b9b3f6fa6
ms.sourcegitcommit: a3ba258f7a8cab5c6d19a3743dd95e904ecebc44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2017
---
# <a name="how-to-determine-which-net-framework-security-updates-and-hotfixes-are-installed"></a>방법: 설치 된.NET Framework 보안 업데이트 및 핫픽스를 결정 합니다.

이 문서에서는.NET Framework 보안 업데이트 확인 하는 방법 및 핫픽스가 컴퓨터에 설치 되어 있습니다.

> [!NOTE]
> 이 문서에 표시 된 모든 기술 관리자 권한이 있는 계정이 필요 합니다.

## <a name="to-find-installed-updates-using-the-registry"></a>찾을 레지스트리를 사용 하 여 업데이트 설치

설치 된 보안 업데이트와 핫픽스는 컴퓨터에 설치 된.NET Framework의 각 버전에 대 한 Windows 레지스트리에 나열 됩니다. 레지스트리 편집기를 사용할 수 있습니다 (*regedit.exe*)이이 정보를 보려면 프로그램입니다.

1. **regedit.exe** 프로그램을 엽니다. Windows 8 이상 버전에서 마우스 오른쪽 단추로 클릭 **시작** ![Windows 로고](../get-started/media/windowskeyboardlogo.png "Windowskeyboardlogo")을 선택한 후 **실행**합니다. 에 **열려** 상자에 입력 **regedit** 선택 **확인**합니다.

2. 레지스트리 편집기에서 다음 하위 키를 엽니다.

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates`

     설치된 업데이트가 적용되는 .NET Framework 버전을 식별하는 하위 키 아래에 나열됩니다. 각 업데이트는 KB(기술 자료) 번호로 식별됩니다.

레지스트리 편집기에서 .NET Framework 버전과 각 버전에 대해 설치된 업데이트는 서로 다른 하위 키에 저장되어 있습니다. 설치 된 버전 번호를 검색 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 설치 된.NET Framework 버전 결정](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)합니다.

## <a name="to-find-installed-updates-by-querying-the-registry-in-code"></a>코드로 레지스트리를에서 쿼리하여 설치 된 업데이트를 찾으려면

다음 예제에는.NET Framework 보안 업데이트와 컴퓨터에 설치 된 핫픽스를 프로그래밍 방식으로 결정 합니다.

[!code-csharp[ListUpdates](../../../samples/snippets/csharp/VS_Snippets_CLR/listupdates/cs/program.cs)]
[!code-vb[ListUpdates](../../../samples/snippets/visualbasic/VS_Snippets_CLR/listupdates/vb/program.vb)]

이 예제에서는 다음과 유사한 출력을 생성 합니다.

```console
Microsoft .NET Framework 4 Client Profile
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
Microsoft .NET Framework 4 Extended
  KB2468871
  KB2468871v2
  KB2478063
  KB2533523
  KB2544514
  KB2600211
  KB2600217
```

## <a name="to-find-installed-updates-by-querying-the-registry-in-powershell"></a>PowerShell에서 레지스트리를 쿼리하여 설치 된 업데이트를 찾으려면

다음 예제에서는.NET Framework 보안 업데이트 및 PowerShell을 사용 하는 컴퓨터에 설치 된 핫픽스를 확인 하는 방법을 보여 줍니다.

```powershell
 Get-ChildItem "HKLM:SOFTWARE\Wow6432Node\Microsoft\Updates\*" -Recurse | Where-Object {$_.name -like
 "*.NET Framework*"}
```

이 예제에서는 다음과 유사한 출력을 생성 합니다.

```console
    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Client Profile


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y


    Hive: HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Updates\Microsoft .NET Framework 4 Extended


Name                           Property
----                           --------
KB2468871                      ThisVersionInstalled : Y
KB2468871v2                    ThisVersionInstalled : Y
KB2478063                      ThisVersionInstalled : Y
KB2533523                      ThisVersionInstalled : Y
KB2544514                      ThisVersionInstalled : Y
KB2600211                      ThisVersionInstalled : Y
KB2600217                      ThisVersionInstalled : Y
```

## <a name="see-also"></a>참고 항목

[방법: 설치 된.NET Framework 버전 확인](../../../docs/framework/migration-guide/how-to-determine-which-versions-are-installed.md)  
[개발자를 위한.NET Framework를 설치 합니다.](../../../docs/framework/install/guide-for-developers.md)  
[버전 및 종속성](../../../docs/framework/migration-guide/versions-and-dependencies.md)
