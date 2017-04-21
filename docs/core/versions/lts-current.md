---
title: ".NET Core 지원 | Microsoft 문서"
description: ".NET Core에 대한 여러 릴리스 트레인 지원(LTS 및 현재)에 대해 알아봅니다."
keywords: ".NET, .NET Core, lts, 현재, fts, 지원, 지원 트레인, 지원 트랙, 수명 주기, 릴리스 트레인"
author: kendrahavens
ms.author: mairaw
ms.date: 01/30/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: fedc7025-f320-4cba-957b-ef74885f66de
translationtype: Human Translation
ms.sourcegitcommit: 1ef17b16b85c81a0b96bb1712db3734dc67d801d
ms.openlocfilehash: 582a521e6a30b740465890b6cb8c773061a98ea6
ms.lasthandoff: 02/07/2017

---

# <a name="net-core-support"></a>.NET Core 지원

.NET Core 지원에 대한 일반적인 설명입니다.

## <a name="lts-and-current-release-trains"></a>LTS 및 현재 릴리스 트레인

두 개의 지원 릴리스 트레인이 있는 것은 소프트웨어 환경 특히, .NET Core와 같은 오픈 프로젝트 전반에서 일반적으로 사용되는 개념입니다. .NET Core에는 [LTS(장기 지원)](https://en.wikipedia.org/wiki/Long-term_support) 및 현재라는 두 가지 지원 릴리스 트레인이 있습니다. LTS 릴리스는 중요한 문제에 대한 수정 및 보안 수정을 수신하여 수명 주기 동안 안정성을 유지합니다. 현재 릴리스에서는 새 기능이 작동되고 추가 버그 수정이 수행됩니다. 지원 관점에서 이러한 릴리스 트레인에는 다음과 같은 지원 수명 주기 특성이 있습니다.

LTS 릴리스:
* LTS의 일반 공급 날짜 이후 3년 동안 지원됩니다.
* 또는 후속 LTS 릴리스의 일반 공급 후 1년 동안 지원됩니다.

현재 릴리스:
* 부모 LTS 릴리스와 동일한 3년 기간 내에서 지원됩니다.
* 후속 현재 릴리스의 일반 공급 후 3개월 동안 지원됩니다.
* 그리고 후속 LTS 릴리스의 일반 공급 후 1년 동안 지원됩니다.

## <a name="versioning"></a>버전 관리
새 LTS 릴리스는 주 버전 번호가 증가됩니다. 현재 릴리스는 해당하는 LTS 트레인과 주 번호가 동일하고 부 버전 번호가 증가됩니다. 예를 들어 LTS는 1.0.3이 되고 현재는 1.1.0이 됩니다. 어느 한 트레인의 버그 수정 업데이트가 수행되면 패치 버전이 증가합니다. 버전 관리 체계에 대한 자세한 내용은 [.NET Core 버전 관리](index.md)를 참조하세요.

## <a name="what-causes-updates-in-lts-and-current-trains"></a>LTS 및 현재 트레인에서 업데이트가 수행되는 이유는 무엇인가요?
버그 수정 또는 API 추가와 같이 버전 번호가 업데이트되게 하는 변경 사항에 대해 알아보려면 [버전 관리 설명서](index.md)의 의사 결정 트리를 참조하세요. 어떤 변경 사항으로 현재 릴리스에서 LTS 분기가 생성되는지를 결정하는 기본 규칙은 없습니다. 일반적으로 필요한 동작을 수정하는 필수 보안 업데이트 및 패치로 인해 LTS 분기가 업데이트됩니다. 또한 항상 가능한 것은 아니지만 LTS 분기에서 최신 데스크톱 개발자 운영 체제를 지원하기 위한 것이기도 합니다. 특정 릴리스에서 지원되는 API, 수정 및 운영 체제를 파악하는 좋은 방법은 GitHub에서 [릴리스 정보](https://github.com/dotnet/core/tree/master/release-notes)를 검색하는 것입니다.

### <a name="further-reading"></a>추가 정보
* [.NET Core Support Lifecycle Fact Sheet](https://www.microsoft.com/net/core/support)(.NET Core 지원 수명 주기 팩트 시트)
* [Currently supported operating systems and versions](https://github.com/dotnet/core/blob/master/roadmap.md)(현재 지원되는 운영 체제 및 버전)
