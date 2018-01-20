---
title: "파이프라인 개발"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add-in pipeline [.NET Framework], segments
- activation path for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], activation path
- communication pipeline for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], pipeline development
ms.assetid: 932788f2-b87d-44cf-82f9-04492a8b2722
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33646bbd7b0043cb5fc036b9b11aa4cf37cd537f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="pipeline-development"></a>파이프라인 개발
추가 기능 파이프라인에는 서로 통신 하는 호스트 응용 프로그램 및 해당 추가 기능을 사용 해야 하는 파이프라인 세그먼트의 경로입니다.  
  
 다음 그림에서는 통신 파이프라인 및 해당 세그먼트를 보여 줍니다.  
  
 ![추가 &#45; 파이프라인 모델입니다. ] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")  
추가 기능 파이프라인  
  
 호스트 응용 프로그램 파이프라인의 한쪽 끝에 있고 다른 쪽 end에는 추가 기능에 있습니다. 한쪽 끝에서 시작 하 고 가운데 방향으로 이동, 호스트 응용 프로그램과 추가 기능을 모두 공유 하는 개체 모델의 뷰를 정의 하는 추상 기본 클래스가 있어야 합니다. 이러한 형식 (클래스)은 보기에서 추가 기능 파이프라인 세그먼트 및 추가 기능 파이프라인 세그먼트의 [호스트] 보기를 구성 합니다. 뷰 추가 기능 파이프라인 세그먼트 종종 둘 이상의 추상 클래스를 포함 하지만 클래스에서 상속 되는 추가 기능에 추가 기능 기본 라고 합니다.  
  
 추가 기능 측 어댑터 파이프라인 세그먼트 및 호스트 측 어댑터 파이프라인 세그먼트 convert 해당 뷰 파이프라인 세그먼트 사이의 계약 파이프라인 세그먼트 형식의 흐름. 파이프라인의 중앙 세그먼트는 계약에서 파생 되는 <xref:System.AddIn.Contract.IContract> 인터페이스입니다. 이 계약은 호스트 응용 프로그램 및 해당 추가 기능에 둘 다를 사용 하는 메서드를 정의 합니다.  
  
 개별 응용 프로그램 도메인에는 호스트와 추가 기능을 로드 하는 경우 추가 기능에 범위에서 호스트 응용 프로그램의 범위를 구분 하는 격리 경계를 해야 합니다. 계약은 호스트와 추가 기능 응용 프로그램 도메인에 로드 된 어셈블리에만입니다. 호스트와 추가 기능을 각 계약 메서드의 해당 보기에만 참조 하십시오. 계약에서 추상화 계층으로 구분 됩니다.  
  
 파이프라인 세그먼트를 개발 하려면 디렉터리 구조에 포함 될 만들어야 합니다. 개발 요구 사항 및 범위 지침에 대 한 자세한 내용은 참조 [파이프라인 개발 요구 사항](http://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)합니다.  
  
 다음 그림은 파이프라인 세그먼트를 구성 하는 형식을 나타냅니다. 그림에 표시 된 형식의 이름이 임의적 이지만 정보 저장소를 생성 하는 방법으로 검색할 수 있도록 호스트와 호스트를 제외 하 고 모든 형식 보기 특성이 추가 기능에 필요 합니다.  
  
 ![추가 &#45; 형식에 대 한 필수 특성이 있는 모델. ] (../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")  
추가 기능 파이프라인 형식  
  
 다음 표에서 추가 기능을 활성화 하는 데 파이프라인 세그먼트에 설명 합니다. 이러한 세그먼트에 대 한 자세한 내용은 참조 [계약, 뷰 및 어댑터](http://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)합니다.  
  
|파이프라인 세그먼트|설명|  
|----------------------|-----------------|  
|호스트|응용 프로그램 어셈블리의 추가 기능 인스턴스를 만듭니다.|  
|추가 기능의 호스트 뷰|호스트 응용 프로그램의 뷰를 개체 형식 및 추가 기능으로 통신 하는 데 사용 되는 메서드를 나타냅니다. [호스트] 보기는 추상 기본 클래스 또는 인터페이스입니다.|  
|호스트 측 어댑터|계약에서 메서드를 변경 하는 하나 또는 그 이상의 클래스가 있는 어셈블리입니다.<br /><br /> 이 파이프라인 세그먼트를 사용 하 여 식별 되는 <xref:System.AddIn.Pipeline.HostAdapterAttribute> 특성입니다.<br /><br /> 다중 모듈 어셈블리가 지원 되지 않습니다.|  
|계약|파생 된 인터페이스는 <xref:System.AddIn.Contract.IContract> 정의 하는 인터페이스 형식을 호스트와 해당 추가 기능에서 간에 통신 하기 위한 프로토콜입니다.<br /><br /> 이 파이프라인 세그먼트를 설정 하 여 식별 되는 <xref:System.AddIn.Pipeline.AddInContractAttribute> 특성입니다.|  
|추가 기능 측 어댑터|계약에서 메서드를 변경 하는 하나 또는 그 이상의 클래스가 있는 어셈블리입니다.<br /><br /> 이 파이프라인 세그먼트를 사용 하 여 식별 되는 <xref:System.AddIn.Pipeline.AddInAdapterAttribute> 특성입니다.<br /><br /> 각 어셈블리에 있는 형식을 포함 하는 추가 기능 측 어댑터 디렉터리는 <xref:System.AddIn.Pipeline.AddInAdapterAttribute> 특성에 대 한 추가 기능 응용 프로그램 도메인에 로드 됩니다.<br /><br /> 추가 기능 측 디렉터리의 각 어셈블리는 자체 응용 프로그램 도메인에 로드 됩니다.<br /><br /> 다중 모듈 어셈블리가 지원 되지 않습니다.|  
|추가 기능에서 보기|어셈블리에 대 한 추가 기능 뷰 개체 유형과 호스트와 통신 하는 데 사용 되는 메서드를 나타내는입니다. 추가 기능을 보기에는 추상 기본 클래스 또는 인터페이스입니다.<br /><br /> 이 파이프라인 세그먼트를 사용 하 여 식별 되는 <xref:System.AddIn.Pipeline.AddInBaseAttribute> 특성입니다.<br /><br /> 각 어셈블리에 있는 형식을 포함 하는 AddInViews 디렉터리는 <xref:System.AddIn.Pipeline.AddInBaseAttribute> 특성에 대 한 추가 기능 응용 프로그램 도메인에 로드 됩니다.|  
|추가 기능|호스트에 대 한 서비스를 수행 하는 인스턴스화된 형식입니다.|  
  
## <a name="pipeline-activation-path"></a>파이프라인 활성화 경로  
 다음 그림에서는 추가 기능을 활성화 될 때 형식의 활성화를 보여 줍니다. 또한 개체를 전달 하는 계산 또는 개체의 컬렉션 결과 등 호스트를 보여 줍니다. 가장 일반적인 시나리오입니다.  
  
 ![추가 &#45; 모델 활성화 경로 사용 합니다. ] (../../../docs/framework/add-ins/media/addin6.png "AddIn6")  
호스트에 추가 기능에서 활성화 경로  
  
 파이프라인의 활성화 경로 다음과 같이 발생합니다.  
  
1.  호스트 응용 프로그램에서 추가 기능 활성화는 <xref:System.AddIn.Hosting.AddInToken.Activate%2A> 메서드.  
  
2.  추가 기능, 추가 기능을 보기, 추가 기능 측 어댑터 및 계약 어셈블리에 대 한 추가 기능 응용 프로그램 도메인에 로드 됩니다.  
  
3.  추가 기능에서 보기를 사용 하 여 추가 기능 측 어댑터의 인스턴스를 만들 (로 식별 되는 클래스와는 <xref:System.AddIn.Pipeline.AddInBaseAttribute> 특성) 생성자로 합니다. 추가 기능 측 어댑터는 계약에서 상속합니다.  
  
4.  계약으로 형식화 된 추가 기능 측 어댑터 (선택 사항) 격리 경계를 넘어 호스트 측 어댑터 생성자로 전달 됩니다.  
  
5.  추가 기능, 호스트 측 어댑터와 계약 어셈블리의 [호스트] 보기에서 호스트 응용 프로그램 도메인에 로드 됩니다.  
  
6.  호스트 측 어댑터의 인스턴스를 생성자로 계약을 사용 하 여 만들어집니다. 호스트 측 어댑터의 추가 기능 [호스트] 보기에서 상속 됩니다.  
  
7.  추가 기능, 호스트는 추가 기능에 보고 하 고 해당 메서드 호출을 계속할 수 형식화 된 호스트에 있습니다.  
  
## <a name="walkthroughs"></a>연습  
 Visual Studio를 사용 하 여 파이프라인을 만드는 방법을 설명 하는 연습 항목에서는 세 가지가 있습니다.  
  
-   [연습: 확장 가능한 응용 프로그램 만들기](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     계산기 추가 기능에 호스트에 대 한 더하기, 빼기, 곱하기 및 나누기 계산을 수행 하는 설명 합니다.  
  
-   [연습: 호스트 변경으로 이전 버전과 호환성을 사용 하도록 설정](http://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     계산기 추가 기능을 향상 된 계산 기능 및 첫 번째는 계산기 추가 기능으로 호환성을 유지 하는 방법을 설명 합니다.  
  
-   [연습: 호스트와 추가 기능 간에 컬렉션 전달](http://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     서 점 시나리오를 사용 하 여 파이프라인을 통해 데이터 컬렉션을 전달 하는 방법을 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [파이프라인 시나리오 추가 기능을](http://msdn.microsoft.com/library/feb70e0b-8734-494c-aeaf-b567f014043e)  
 [추가 기능 및 확장성](../../../docs/framework/add-ins/index.md)
