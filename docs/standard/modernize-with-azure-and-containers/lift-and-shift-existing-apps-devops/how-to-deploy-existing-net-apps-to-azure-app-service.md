---
title: Azure 앱 서비스를 기존.NET 응용 프로그램을 배포 하는 방법
description: 컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Azure 앱 서비스를 기존.NET 응용 프로그램을 배포 하는 방법
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: c1602f718e7623871ebf9d6b5b52289dc2200886
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-deploy-existing-net-apps-to-azure-app-service"></a>Azure 앱 서비스를 기존.NET 응용 프로그램을 배포 하는 방법 

Azure 앱 서비스의 웹 응용 프로그램 기능은 호스팅 웹 사이트 및 웹 응용 프로그램에 최적화 된 계산을 완전히 관리 되는 플랫폼입니다. Microsoft Azure 사용에서이 PaaS 제품 중점을 비즈니스 논리를 실행 하 고 앱의 크기를 조정 하도록 인프라에는 Azure를 담당 하는 동안.

## <a name="validate-sites-and-migrate-to-app-service-with-azure-app-service-migration-assistant"></a>사이트의 유효성을 검사 하 고 있는 Azure 앱 서비스 Migration Assistant 앱 서비스로 마이그레이션

일반적으로 응용 프로그램 서비스에 응용 프로그램을 이동 하는 Visual Studio에서 새 응용 프로그램을 만들 때 하는 것은 간단 합니다. 그러나 응용 프로그램 서비스에는 기존 응용 프로그램을 마이그레이션할 계획 이라면 먼저 응용 프로그램의 모든 종속성은 앱 서비스와 호환 되는지 여부를 평가할 합니다. 서버 운영 체제 및 서버에 설치 된 모든 타사 소프트웨어와 같은 종속성 포함 됩니다.

사용할 수 있습니다 [Azure 앱 서비스 Migration Assistant](https://www.migratetoazure.net/) 를 사이트 분석 한 다음 응용 프로그램 서비스에 Windows 및 Linux 웹 서버에서 마이그레이션할 수 있습니다. 마이그레이션의 일환으로,이 도구는 웹 응용 프로그램을 만듭니다 및 Azure에서 데이터베이스 필요에 따라 콘텐츠를 게시 하 고 데이터베이스를 게시 합니다.

Azure 앱 서비스 Migration Assistant는 클라우드로 Windows Server에서 실행 되는 IIS에서로 마이그레이션하도록 지원 합니다. 응용 프로그램 서비스는 Windows Server 2003 및 이후 버전을 지원합니다.

> ![https://www.migratetoazure.net/Images/ImageCanvas.png](./media/image5.png)
>
> **그림 4-5입니다.** Azure 앱 서비스 마이그레이션 길잡이 사용 하 여

앱 서비스 마이그레이션 도우미는 웹 서버에서 Azure 클라우드 웹 사이트를 이동 하는 도구입니다.

앱 서비스, 웹 사이트를 마이그레이션한 후 사이트에 안전 하 고 효율적으로 실행에 필요한 모든 것입니다. 사이트를 설정 하 고 Azure 클라우드 PaaS 서비스 (앱 서비스)에서 자동으로 실행 됩니다.

앱 서비스 마이그레이션 도구 웹 사이트를 분석 하 고 응용 프로그램 서비스를 이동 하기 위한의 호환성을 보고할 수 있습니다. 분석 만족 했으면 응용 프로그램 서비스 Migration Assistant 콘텐츠, 데이터 및 설정을 마이그레이션할 수 있습니다. 사이트 매우 호환 되지 않으면 마이그레이션 도구를 작동 하도록 조정 해야 알려 줍니다.

### <a name="additional-resources"></a>추가 자료

- **Azure 앱 서비스 마이그레이션 길잡이**

    [https://www.migratetoazure.net/](https://www.migratetoazure.net/)

>[!div class="step-by-step"]
[이전](what-about-cloud-optimized-applications.md)
[다음](deploy-existing-net-apps-as-windows-containers.md)
