---
title: ASP.NET Core 및 Azure를 사용하여 현대식 웹 응용 프로그램 설계
description: ASP.NET Core 및 Azure를 사용하여 모놀리식 웹 응용 프로그램을 빌드하는 방법에 대한 포괄적인 지침을 제공하는 가이드입니다.
author: ardalis
ms.author: wiwagn
ms.date: 06/28/2018
ms.openlocfilehash: e2d2545108b55043c322baffbd609b2422d2743b
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37936986"
---
# <a name="architect-modern-web-applications-with-aspnet-core-and-azure"></a>ASP.NET Core 및 Azure를 사용하여 현대식 웹 응용 프로그램 설계

![표지 이미지](./media/cover.png)

게시자:

Microsoft 개발자 사업부, .NET 및 Visual Studio 제품 팀

Microsoft Corporation의 사업부

One Microsoft Way

Redmond, Washington 98052-6399

Copyright © 2018 by Microsoft Corporation

All rights reserved. 이 가이드의 내용 중 어떤 부분도 게시자의 서면 허가 없이는 어떠한 형식이나 방법으로도 복제하거나 전송할 수 없습니다.

이 가이드는 작성자의 견해와 의견을 “있는 그대로” 제공하고 전달합니다. URL 및 기타 인터넷 웹 사이트 참조를 비롯하여 이 가이드에 제공된 견해, 의견 및 정보는 예고 없이 변경될 수 있습니다.

여기에 설명된 일부 예제는 예시 용도로만 제공되며 실제 데이터가 아닙니다. 실제로 연관시키거나 관련시키려고 의도하거나 추론해서는 안 됩니다.

“상표” 웹 페이지의 https://www.microsoft.com에 나열된 Microsoft 및 상표는 Microsoft 그룹 계열사의 상표입니다.

Mac 및 macOS는 Apple Inc.의 상표입니다.

Docker 고래 로고는 Docker, Inc.의 등록 상표로, 허가하에 사용됩니다.

기타 모든 표시와 로고는 해당 소유자의 자산입니다.

만든 이:

> **Steve Smith(@ardalis)**, 소프트웨어 아키텍처 관리자, [Ardalis.com](https://ardalis.com)

편집자:

> **Maira Wenzel**

## <a name="introduction"></a>소개

.NET core 및 ASP.NET Core는 기존의.NET 개발에 비해 여러 가지 이점을 제공합니다. 다음 중 일부 또는 전부가 응용 프로그램의 성공에 중요한 경우 서버 응용 프로그램에 .NET Core를 사용해야 합니다.

- 플랫폼 간 지원

- 마이크로 서비스 사용

- Docker 컨테이너 사용

- 고성능 및 확장성 요구 사항

- 동일한 서버의 응용 프로그램에서 .NET 버전 병렬 관리

기존 .NET 응용 프로그램은 이러한 요구 사항을 지원할 수 있지만 ASP.NET Core 및 .NET Core는 위의 시나리오에 대한 향상된 지원을 제공하도록 최적화되었습니다.

점점 더 많은 조직에서 Microsoft Azure 같은 서비스를 사용하는 클라우드에 웹 응용 프로그램을 호스팅하기로 선택하고 있습니다. 응용 프로그램 또는 조직에 다음 사항이 중요한 경우 클라우드에서 응용 프로그램을 호스팅하는 것이 좋습니다.

- 데이터 센터 비용에 대한 투자 감소(하드웨어, 소프트웨어, 공간, 유틸리티 등)

- 유동적인 가격 책정(유휴 용량이 아닌 사용량을 기준으로 지불)

- 매우 뛰어난 안정성

- 향상된 앱 이동성: 앱의 배포 위치와 방법을 쉽게 변경

- 유동적인 용량: 실제 요구 사항에 따라 규모 확장 또는 축소

Azure에서 호스팅되는 ASP.NET Core를 사용하여 웹 응용 프로그램을 빌드하면 기존의 대안보다 많은 경쟁적 이점을 제공할 수 있습니다. ASP.NET Core는 현대식 웹 응용 프로그램 개발 사례 및 클라우드 호스팅 시나리오에 최적화되어 있습니다. 이 가이드에서는 이러한 기능을 최대한 활용할 수 있도록 ASP.NET Core 응용 프로그램을 설계하는 방법에 알아봅니다.

## <a name="purpose"></a>용도

이 가이드에서는 ASP.NET Core 및 Azure를 사용하는 모놀리식 웹 응용 프로그램을 구축하는 방법에 대한 포괄적인 지침을 제공합니다.

이 가이드는 ["_.NET 마이크로 서비스를 보완합니다. 컨테이너화된 .NET 응용 프로그램_"](../microservices-architecture/index.md)의 아키텍처는 엔터프라이즈 응용 프로그램을 호스팅하는 Docker, 마이크로 서비스 및 컨테이너의 배포에 중점을 둡니다.

### <a name="net-microservices-architecture-for-containerized-net-applications"></a>.NET 마이크로 서비스. 컨테이너화된 .NET 응용 프로그램을 위한 아키텍처

- **전자책**  
  <https://aka.ms/MicroservicesEbook>
- **예제 응용 프로그램**  
  <https://aka.ms/microservicesarchitecture>

## <a name="who-should-use-this-guide"></a>이 가이드의 대상 사용자

이 가이드의 주요 대상 사용자는 클라우드에서 Microsoft 기술 및 서비스를 사용하여 현대식 웹 응용 프로그램을 구축하는 데 관심 있는 개발자, 개발 책임자 및 설계자입니다.

이차적인 대상 사용자는 이미 ASP.NET 또는 Azure에 익숙하고 신규 또는 기존 프로젝트를 위해 ASP.NET Core를 업그레이드하는 것이 적절한지에 관한 정보를 찾고 있는 기술 의사 결정권자입니다.

## <a name="how-you-can-use-this-guide"></a>이 가이드를 사용하는 방법

이 가이드는 현대식 .NET 기술 및 Windows Azure로 웹 응용 프로그램을 구축하는 방법에 중점을 둔, 비교적 작은 문서로 압축되었습니다. 따라서 전제적으로 읽어보면 이러한 응용 프로그램 및 해당 기술 고려 사항의 이해를 위한 기반을 마련할 수 있습니다. 이 가이드와 응용 프로그램 예제는 출발점이나 참고 자료 역할도 할 수 있습니다. 관련 응용 프로그램 예제를 자신의 응용 프로그램을 위한 템플릿으로 사용하거나 응용 프로그램의 구성 요소 부분을 구성하는 방법을 알아보는 용도로 사용하세요. 자신의 응용 프로그램을 위한 옵션을 저울질할 때는 가이드의 원칙과 아키텍처 및 기술 옵션, 의사 결정 고려 사항에 대한 내용을 참조하세요.

이 가이드를 팀에게 자유롭게 전달하여 이러한 고려 사항 및 기회에 대한 공통적인 이해를 도모하세요. 모든 사람이 공통적인 용어 집합과 기본 원칙으로 작업하도록 하면 아키텍처 패턴과 방법의 일관적인 적용을 보장하는 데 도움이 됩니다.

## <a name="references"></a>참조

- **서버 앱에 대해 .NET Core와 .NET Framework 중에 선택**  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
[다음](modern-web-applications-characteristics.md)
