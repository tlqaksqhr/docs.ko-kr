---
title: Docker 응용 프로그램의 상태 및 데이터
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 83094cd9a13d77f489df639096bb42b23ce152e7
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="state-and-data-in-docker-applications"></a>Docker 응용 프로그램의 상태 및 데이터

컨테이너의 기본 형식은 불변성입니다. VM에 비해, 컨테이너 하지 않는 경우가 종종으로 사라집니다. VM은 배달 못 한 프로세스, 오버 로드 된 CPU 또는 전체 또는 실패 한 디스크에서 다양 한 형태로 실패할 수 있습니다. 아직, VM을 사용할 수 있는 것으로 예상 및 RAID 드라이브는 드라이브 오류 데이터를 유지 관리를 일반화 합니다.

그러나 컨테이너는 프로세스의 인스턴스여야 하 간주 됩니다. 프로세스에는 영구 상태를 유지 되지 않습니다. 로컬 저장소에 컨테이너도 작성할 수 있지만 해당 인스턴스 되도록 주위 무기한 가정 동일 단일 복사 메모리 영 속 수 것으로 가정 합니다. 종료, 프로세스와 같은 컨테이너, 중복 된 이거나 하 컨테이너 orchestrator와 관리 하는 경우 이러한 이동 될 수 있다고 간주 해야 합니다.

이라는 기능을 사용 하 여 docker는 *오버레이 파일 시스템* 기반이 되는 원본 이미지에 비해 컨테이너의 루트 파일 시스템에 업데이트 된 정보를 모두 저장 하는 쓰기 시 복사 프로세스를 구현 합니다. 이후에 시스템에서 컨테이너를 삭제 하는 경우 이러한 변경 내용은 손실 됩니다. 컨테이너에 따라서 않아도 영구 저장소 기본적으로 됩니다. 컨테이너의 상태를 저장할 수 있지만이 시스템 디자인 것과 컨테이너 아키텍처의 원칙 충돌입니다.

Docker는 응용 프로그램에서 영구 데이터를 관리 하는 일반적인 해결입니다.

-   [**데이터 볼륨**](https://docs.docker.com/engine/tutorials/dockervolumes/) 이러한 바로 언급 하지 않는 호스트에 탑재 합니다.

-   [**데이터 볼륨 컨테이너**](https://docs.docker.com/engine/tutorials/dockervolumes/#/creating-and-mounting-a-data-volume-container) 이러한 반복할 수 있는 외부에서 컨테이너를 사용 하 여 컨테이너에서 공유 저장소를 제공 합니다.

-   [**볼륨 플러그 인**](https://docs.docker.com/engine/tutorials/dockervolumes/#/mount-a-shared-storage-volume-as-a-data-volume) 이러한 장기 지 속성을 제공 하는 원격 위치로 볼륨을 탑재 합니다.

-   **원격 데이터 원본** 예제 SQL 및 NO SQL 데이터베이스를 포함 하거나 Redis와 같은 서비스를 캐시 합니다.

-   [**Azure 저장소**](https://docs.microsoft.com/azure/storage/) 지역 배포 가능한 플랫폼으로 장기 지 속성의 컨테이너를 제공 하는 서비스 (PaaS) 저장소로 제공 합니다.

데이터 볼륨 특별 하 게 사용 하지 않는 하나 이상의 컨테이너 내에서 디렉터리를 지정 된 [Union 파일 시스템](https://docs.docker.com/v1.8/reference/glossary#union-file-system)합니다. 데이터 볼륨 컨테이너의 수명 주기에 독립적 데이터를 유지 하기 위해 설계 되었습니다. Docker 따라서 자동으로 삭제 볼륨 컨테이너를 제거 하지 "가비지 수집" 볼륨 컨테이너에 의해 더 이상 참조 되지 않습니다. 호스트 운영 체제 찾아보고 모든 볼륨의 데이터를 데이터 볼륨을 제한적으로 사용 하는 또 다른 이유는 자유롭게 편집할 수 있습니다.

A [데이터 볼륨 컨테이너](https://docs.docker.com/v1.8/userguide/dockervolumes/) 일반 데이터 볼륨 개선 된 합니다. 기본적으로 휴지 컨테이너 (앞에서 설명한) 내에 만들어진 데이터 볼륨을 하나 이상 있는 경우 데이터 볼륨 컨테이너는 중앙 탑재 지점에서 컨테이너에 대한 액세스를 제공합니다. 액세스이 메서드의 장점은 논리 탑재 지점이 데이터 컨테이너를 만드는 원래 데이터의 위치를 추상화 것입니다. "Application" 컨테이너를를 만들고 소멸 전용된 컨테이너에서 영구 데이터를 유지 하면서 데이터 컨테이너 볼륨에 액세스할 수도 있습니다.

그림 4-5를 보여 줍니다 일반의 Docker 볼륨 저장소 컨테이너 자체 되었지만 물리적 호스트 서버/v M 경계 내에 배치할 수 있습니다. *docker 볼륨에 하나의 호스트 서버/v M에서 볼륨을 사용 하는 기능은 없는*합니다.

![](./media/image5.png)

그림 4-5: 데이터 볼륨 및 컨테이너 응용 프로그램/컨테이너에 대 한 외부 데이터 원본

별도 물리적 호스트에서 실행 되는 컨테이너 간에 공유 되는 데이터 관리를 할 수 없는 것이 좋습니다을 사용 하면 볼륨 비즈니스 데이터에 대 한 Docker 호스트에 고정된 호스트/VM 않으면 때문에 orchestrator에서 Docker 컨테이너를 사용 하는 경우 컨테이너를 클러스터에서 수행할 수 있도록 최적화에 따라 다른 호스트를 하나에서 이동 될 예정입니다.

따라서 일반 데이터 볼륨은 추적 파일, 임시 파일을 비슷한 개념이 없습니다 경우 또는 여러 호스트에 컨테이너를 이동할 때 비즈니스 데이터 일관성에 영향을 주는 작업에 적합 한 메커니즘입니다.

볼륨 플러그 인과 같은 [Flocker](https://clusterhq.com/flocker/) 클러스터의 모든 호스트에 걸쳐 데이터를 제공 합니다. 일부 볼륨 플러그 인을 동일 하 게 생성 되더라도 볼륨 플러그 인는 일반적으로 변경할 수 없는 컨테이너에서 영구 표면화 된 신뢰할 수 있는 저장소를 제공 합니다.

원격 데이터 원본 및 SQL 데이터베이스, DocumentDB, 또는 Redis와 같은 원격 캐시와 같은 캐시 컨테이너 없이 개발 동일 해야 합니다. 비즈니스 응용 프로그램 데이터를 저장 하는 기본 설정, 및 검증 된 방법 중 하나입니다.


>[!div class="step-by-step"]
[이전] (모놀리식-applications.md) [다음] (soa applications.md)
