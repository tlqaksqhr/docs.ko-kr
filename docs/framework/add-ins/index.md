---
title: 추가 기능 및 확장성
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- extensibility [.NET Framework], add-ins
- add-ins [.NET Framework]
- add-ins [.NET Framework], about
- hosts [.NET Framework], compared to add-ins
- .NET Framework, add-ins
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], compared to hosts
- .NET Framework, extensibility
- versioning [.NET Framework], add-ins
ms.assetid: 8dd45b02-7218-40f9-857d-40d7b98b850b
caps.latest.revision: 42
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d288d321063512f91ad94b417bb1a6bf38c9ef9
ms.sourcegitcommit: cf22b29db780e532e1090c6e755aa52d28273fa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="add-ins-and-extensibility"></a>추가 기능 및 확장성
<a name="top"></a> 추가 기능은 호스트 응용 프로그램에 대한 확장명 기능이나 서비스를 제공합니다. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 에서는 개발자가 추가 기능을 개발하고 호스트 응용 프로그램에서 활성화하는 데 사용할 수 있는 프로그래밍 모델을 제공합니다. 모델은 이 작업을 위해 호스트와 추가 기능 간에 통신 파이프라인을 생성합니다. 모델은 <xref:System.AddIn>, <xref:System.AddIn.Hosting>, <xref:System.AddIn.Pipeline>및 <xref:System.AddIn.Contract> 네임스페이스의 형식을 사용하여 구현됩니다.  
  
 이 개요는 다음과 같은 단원으로 구성됩니다.  
  
-   [추가 기능 모델](#addin_model)  
  
-   [추가 기능 및 호스트 구별](#distinguishing_between_addins_and_hosts)  
  
-   [관련 항목](#related_topics)  
  
-   [참조](#reference)  
  
> [!NOTE]
>  추가 기능 파이프라인 빌드를 위한 도구의 고객 기술 미리 보기 및 추가 샘플 코드는 [CodePlex의 관리되는 확장성 및 추가 기능 프레임워크 사이트](http://go.microsoft.com/fwlink/?LinkId=121190)(영문)를 참조하세요.  
  
<a name="addin_model"></a>   
## <a name="add-in-model"></a>추가 기능 모델  
 추가 기능 모델은 추가 기능과 호스트 간의 모든 통신을 담당하는, 추가 기능 파이프라인(통신 파이프라인이라고도 함)을 구성하는 일련의 세그먼트로 이루어져 있습니다. 파이프라인은 추가 기능과 해당 호스트 간에 데이터를 교환하는 세그먼트의 대칭 통신 모델입니다. 호스트와 추가 기능 간에 이러한 세그먼트를 개발하면 추가 기능의 버전 관리 및 격리를 지원하는 필수 추상화 계층이 제공됩니다.  
  
 다음 그림에서는 파이프라인을 보여 줍니다.  
  
 ![추가 &#45; 파이프라인 모델입니다. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
추가 기능 파이프라인  
  
 이러한 세그먼트에 대한 어셈블리가 동일한 응용 프로그램 도메인에 있을 필요는 없습니다. 고유한 새 응용 프로그램 도메인, 기존 응용 프로그램 도메인 또는 호스트의 응용 프로그램 도메인에 추가 기능을 로드할 수 있습니다. 동일한 응용 프로그램 도메인에 여러 추가 기능을 로드할 수 있으며, 이 경우 추가 기능이 리소스와 보안 컨텍스트를 공유할 수 있습니다.  
  
 추가 기능 모델은 호스트와 추가 기능 간에 격리 경계(원격 경계라고도 함)라는 선택적 경계를 지원하고 권장합니다. 이 경계는 응용 프로그램 도메인 또는 프로세스 경계일 수 있습니다.  
  
 파이프라인 중간에 있는 계약 세그먼트는 호스트의 응용 프로그램 도메인과 추가 기능의 응용 프로그램 도메인 둘 다에 로드됩니다. 계약은 호스트와 추가 기능이 서로 형식을 교환하는 데 사용하는 가상 메서드를 정의합니다.  
  
 격리 경계를 통과하려면 형식이 계약 또는 직렬화 가능 형식이어야 합니다. 계약 또는 직렬화 가능 형식이 아닌 형식은 파이프라인의 어댑터 세그먼트에 의해 계약으로 변환되어야 합니다.  
  
 파이프라인의 보기 세그먼트는 계약에 정의된 대로 호스트와 추가 기능에 공유하는 메서드 뷰를 제공하는 추상 기본 클래스 또는 인터페이스입니다.  
  
 파이프라인 세그먼트 개발에 대한 자세한 내용은 [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)을 참조하세요.  
  
 이후 섹션에서는 추가 기능 모델의 기능을 설명합니다.  
  
### <a name="independent-versioning"></a>독립된 버전 관리  
 추가 기능 모델을 사용하면 호스트와 추가 기능 버전을 독립적으로 관리할 수 있습니다. 따라서 추가 기능 모델은 다음 시나리오를 가능하게 합니다.  
  
-   호스트가 이전 버전의 호스트용으로 빌드된 추가 기능을 사용할 수 있게 해주는 어댑터 만들기  
  
-   호스트가 이후 버전의 호스트용으로 빌드된 추가 기능을 사용할 수 있게 해주는 어댑터 만들기  
  
-   호스트가 다른 호스트용으로 빌드된 추가 기능을 사용할 수 있게 해주는 어댑터 만들기  
  
### <a name="discovery-and-activation"></a>검색 및 활성화  
 정보 저장소에서 발견된 추가 기능을 나타내는 컬렉션의 토큰을 사용하여 추가 기능을 활성화할 수 있습니다. 추가 기능은 추가 기능의 호스트 뷰를 정의하는 형식을 검색하여 찾습니다. 추가 기능을 정의하는 형식을 기준으로 특정 추가 기능을 찾을 수도 있습니다. 정보 저장소는 파이프라인 저장소와 추가 기능 저장소라는 두 개의 캐시 파일로 구성됩니다.  
  
 업데이트 및 정보 저장소를 다시 작성 하는 방법에 대 한 정보를 참조 하십시오. [추가 기능 검색](http://msdn.microsoft.com/library/5d268dde-11df-4c4d-a022-f58d88bbc421)합니다. 추가 기능을 활성화 하는 방법에 대 한 정보를 참조 하십시오. [추가 기능 활성화](http://msdn.microsoft.com/library/bedcbcdf-5964-4215-b5f3-3299798b2b3f) 및 [하는 방법: 다양 한 격리 및 보안을 사용 하 여 추가 기능을 활성화](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5)합니다.  
  
### <a name="isolation-levels-and-external-processes"></a>격리 수준 및 외부 프로세스  
 추가 기능 모델은 추가 기능과 해당 호스트 간에 또는 추가 기능 간에 여러 수준의 격리를 지원합니다. 최소 격리부터 시작하여 이러한 수준은 다음과 같습니다.  
  
-   추가 기능이 호스트와 동일한 응용 프로그램 도메인에서 실행됩니다. 이 경우 다른 응용 프로그램 도메인을 사용할 때 얻을 수 있는 격리 및 언로드 기능이 손실되므로 권장되지 않습니다.  
  
-   여러 추가 기능이 호스트에서 사용하는 응용 프로그램 도메인과 다른 동일한 응용 프로그램 도메인에 로드됩니다.  
  
-   각 추가 기능이 배타적으로 고유한 응용 프로그램 도메인에 로드됩니다. 이는 가장 일반적인 격리 수준입니다.  
  
-   여러 추가 기능이 외부 프로세스에서 동일한 응용 프로그램 도메인에 로드됩니다.  
  
-   각 추가 기능이 외부 프로세스에서 배타적으로 고유한 응용 프로그램 도메인에 로드됩니다. 이는 가장 격리된 시나리오입니다.  
  
 외부 프로세스를 사용 하는 방법에 대 한 자세한 내용은 참조 [하는 방법: 다양 한 격리 및 보안을 사용 하 여 추가 기능을 활성화](http://msdn.microsoft.com/library/7afe7ec8-5158-4350-9119-5df0ecab8aa5)합니다.  
  
### <a name="lifetime-management"></a>수명 관리  
 추가 기능 모델은 응용 프로그램 도메인 및 프로세스 경계에 걸쳐 있으므로 가비지 수집만으로는 개체를 해제하고 확보하기에 충분하지 않습니다. 추가 기능 모델은 토큰 및 참조 횟수를 사용하며 일반적으로 추가 프로그래밍이 필요하지 않은 수명 관리 메커니즘을 제공합니다. 자세한 내용은 참조 [수명 관리](http://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)합니다.  
  
 [맨 위로 이동](#top)  
  
<a name="distinguishing_between_addins_and_hosts"></a>   
## <a name="distinguishing-between-add-ins-and-hosts"></a>추가 기능 및 호스트 구별  
 추가 기능과 호스트의 차이점은 단지 호스트가 추가 기능을 활성화한다는 것입니다. 호스트는 워드프로세싱 응용 프로그램과 해당 맞춤법 검사기와 같이 둘 중에서 더 큰 것이거나, 미디어 플레이어를 포함하는 인스턴트 메시징 클라이언트와 같이 둘 중에서 더 작은 것일 수 있습니다. 추가 기능 모델은 클라이언트 및 서버 시나리오 둘 다에서 추가 기능을 지원합니다. 서버 추가 기능의 예로는 메일 서버에 바이러스 검사, 스팸 필터 및 IP 보호를 제공하는 추가 기능이 있습니다. 클라이언트 추가 기능에서 예로 워드 프로세서, 그래픽 프로그램 및 게임 및 로컬 전자 메일 클라이언트용 바이러스 검색이 특수 기능에 대 한 참조 추가 기능입니다.  
  
 [맨 위로 이동](#top)  
  
<a name="related_topics"></a>   
## <a name="related-topics"></a>관련 항목  
  
|제목|설명|  
|-----------|-----------------|  
|[Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)|호스트 응용 프로그램과 추가 기능 간의 세그먼트 통신 파이프라인을 설명합니다. 파이프라인을 생성하는 방법 및 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 세그먼트를 파이프라인에 배포하는 방법을 설명하는 코드 예제를 연습 항목에서 제공합니다.|  
|[응용 프로그램 도메인 및 어셈블리](http://msdn.microsoft.com/library/433b04ae-4ba8-4849-9dbd-79194f240346)|보안, 안정성 및 버전 관리를 위한 격리 경계를 제공하는 응용 프로그램 도메인과 어셈블리 간의 관계를 설명합니다.|  
  
 [맨 위로 이동](#top)  
  
<a name="reference"></a>   
## <a name="reference"></a>참조  
 <xref:System.AddIn?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Contract?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Hosting?displayProperty=nameWithType>  
  
 <xref:System.AddIn.Pipeline?displayProperty=nameWithType>  
  
 [맨 위로 이동](#top)