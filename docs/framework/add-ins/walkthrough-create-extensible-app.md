---
title: "연습: 확장 가능한 응용 프로그램 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6609f30844421f94965fbe05114db96ed8edbb31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-an-extensible-application"></a>연습: 확장 가능한 응용 프로그램 만들기
이 연습에는 추가 기능에 대 한 간단한 계산기 기능을 수행 하는 파이프라인을 만드는 방법을 설명 합니다. 실제 시나리오; 보여 주지 않습니다. 대신, 파이프라인 및 방법을 추가 기능에서 서비스를 제공할 수는 호스트의 기본 기능을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 설명합니다.  
  
-   Visual Studio 솔루션을 만드는 중입니다.  
  
-   파이프라인 디렉터리 구조를 만듭니다.  
  
-   계약 및 뷰 만들기  
  
-   추가 기능 측 어댑터 만들기  
  
-   호스트 측 어댑터 만들기  
  
-   호스트 만들기  
  
-   추가 기능을 만드는 중입니다.  
  
-   파이프라인을 배포 합니다.  
  
-   호스트 응용 프로그램을 실행 합니다.  
  
 이 파이프라인만 serializable 형식 전달 (<xref:System.Double> 및 <xref:System.String>), 호스트와 추가 기능 사이입니다. 복잡 한 데이터 형식의 컬렉션을 전달 하는 방법을 보여 주는 예제를 보려면 [연습: 호스트 간에 컬렉션 전달 및 추가 기능](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)합니다.  
  
 4 개의 산술 연산의 개체 모델을 정의 하는이 파이프라인에 대 한 계약: 추가, 빼기, 곱하기 및 나누기입니다. 예: 2 + 2를 계산 하는 수식으로 호스트를 추가 기능을 제공 하 고 추가 기능을 호스트에 결과 반환 합니다.  
  
 버전 2는 계산기 추가 기능에 추가 계산 기능을 제공 하 고 버전 관리를 보여 줍니다. 에 설명 되어 [연습: 내용은 이전 버전과 호환성 활성화](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 진행하려면 먼저 다음 작업을 수행해야 합니다.  
  
-   [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].  
  
## <a name="creating-a-visual-studio-solution"></a>Visual Studio 솔루션 만들기  
 솔루션을 사용 하 여 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 파이프라인 세그먼트의 프로젝트를 포함 하도록 합니다.  
  
#### <a name="to-create-the-pipeline-solution"></a>파이프라인 솔루션을 만들려면  
  
1.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], 라는 새 프로젝트를 만들 `Calc1Contract`합니다. 기반으로 **클래스 라이브러리** 템플릿.  
  
2.  솔루션 이름을 `CalculatorV1`합니다.  
  
## <a name="creating-the-pipeline-directory-structure"></a>파이프라인 디렉터리 구조 만들기  
 추가 기능 모델에는 지정 된 디렉터리 구조에 배치 될 파이프라인 세그먼트 어셈블리 필요 합니다. 파이프라인 구조에 대 한 자세한 내용은 참조 [파이프라인 개발 요구 사항](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)합니다.  
  
#### <a name="to-create-the-pipeline-directory-structure"></a>파이프라인 디렉터리 구조를 만들려면  
  
1.  아무 곳 이나 컴퓨터에 응용 프로그램 폴더를 만듭니다.  
  
2.  해당 폴더에는 다음과 같은 구조를 만듭니다.  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     응용 프로그램 폴더;에 파이프라인 폴더 구조를 배치할 필요는 없습니다. 편의 위해서만 여기 수행 됩니다. 적절 한 단계에서 파이프라인 폴더 구조를 다른 위치에 있으면 코드를 변경 하는 방법을 설명 합니다. 디렉터리 요구 사항에 파이프라인의 설명을 참조 [파이프라인 개발 요구 사항](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)합니다.  
  
    > [!NOTE]
    >  `CalcV2` 폴더는이 연습에서 사용 되지 않으므로 자리 표시자 [연습: 내용은 이전 버전과 호환성 활성화](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)합니다.  
  
## <a name="creating-the-contract-and-views"></a>계약 및 뷰 만들기  
 이 파이프라인에 있는 계약 세그먼트 정의 `ICalc1Contract` 네 가지 메서드를 정의 하는 인터페이스: `add`, `subtract`, `multiply`, 및 `divide`합니다.  
  
#### <a name="to-create-the-contract"></a>계약을 만들려면  
  
1.  라는 Visual Studio 솔루션에 `CalculatorV1`열고는 `Calc1Contract` 프로젝트.  
  
2.  **솔루션 탐색기**에 다음 어셈블리에 대 한 참조 추가 `Calc1Contract` 프로젝트:  
  
     System.AddIn.Contract.dll  
  
     탐색기  
  
3.  **솔루션 탐색기**에 새로 추가 되는 기본 클래스 제외 **클래스 라이브러리** 프로젝트.  
  
4.  **솔루션 탐색기**, 프로젝트에 새 항목 추가 사용 하는 **인터페이스** 서식 파일입니다. 에 **새 항목 추가** 대화 상자는 인터페이스 이름 `ICalc1Contract`합니다.  
  
5.  인터페이스 파일에서 네임 스페이스 참조를 추가 <xref:System.AddIn.Contract> 및 <xref:System.AddIn.Pipeline>합니다.  
  
6.  다음 코드를 사용 하 여이 계약 세그먼트를 완료 합니다. 이 인터페이스는 <xref:System.AddIn.Pipeline.AddInContractAttribute> 특성입니다.  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  필요에 따라 Visual Studio 솔루션을 빌드하십시오. 최종 절차 이지만 각 절차는 각 프로젝트 인지 확인 한 후 빌드 해결 될 때까지 솔루션을 실행할 수 없습니다.  
  
 추가 기능을 보기와 호스트의 볼 있기 때문에 추가 기능을 일반적으로 동일한 코드를 갖는 첫 번째 버전의 추가 기능에서 특히, 동시에 뷰를 쉽게 만들 수 있습니다. 오직 1 단계에 따라 달라 집니다: 추가 기능을 보기는 <xref:System.AddIn.Pipeline.AddInBaseAttribute> 추가 기능의 호스트 뷰 특성이 필요 하지 않지만 특성입니다.  
  
#### <a name="to-create-the-add-in-view"></a>추가 기능에서 보기를 만들려면  
  
1.  라는 새 프로젝트 추가 `Calc1AddInView` 에 `CalculatorV1` 솔루션입니다. 기반으로 **클래스 라이브러리** 템플릿.  
  
2.  **솔루션 탐색기**를 탐색기에 대 한 참조 추가 `Calc1AddInView` 프로젝트.  
  
3.  **솔루션 탐색기**에 새로 추가 되는 기본 클래스 제외 **클래스 라이브러리** 프로젝트, 프로젝트에 새 항목 추가 및 사용 하 여는 **인터페이스** 템플릿. 에 **새 항목 추가** 대화 상자는 인터페이스 이름 `ICalculator`합니다.  
  
4.  인터페이스 파일에서 네임 스페이스 참조를 추가 <xref:System.AddIn.Pipeline>합니다.  
  
5.  이 추가 기능에서 보기를 완료 하려면 다음 코드를 사용 합니다. 이 인터페이스는 <xref:System.AddIn.Pipeline.AddInBaseAttribute> 특성입니다.  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  필요에 따라 Visual Studio 솔루션을 빌드하십시오.  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a>추가 기능의 호스트 뷰를 만들려면  
  
1.  라는 새 프로젝트 추가 `Calc1HVA` 에 `CalculatorV1` 솔루션입니다. 기반으로 **클래스 라이브러리** 템플릿.  
  
2.  **솔루션 탐색기**에 새로 추가 되는 기본 클래스 제외 **클래스 라이브러리** 프로젝트, 프로젝트에 새 항목 추가 및 사용 하 여는 **인터페이스** 템플릿. 에 **새 항목 추가** 대화 상자는 인터페이스 이름 `ICalculator`합니다.  
  
3.  인터페이스 파일에서 추가 기능의 호스트 뷰를 완료 하려면 다음 코드를 사용 합니다.  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  필요에 따라 Visual Studio 솔루션을 빌드하십시오.  
  
## <a name="creating-the-add-in-side-adapter"></a>추가 기능 측 어댑터 만들기  
 이 추가 기능 측 어댑터는 하나의 보기-계약으로 구성 됩니다. 이 파이프라인 세그먼트에서 추가 기능 보기에서 계약 형식을 변환합니다.  
  
 이 파이프라인에 추가 기능에 호스트에 서비스를 제공 하 고 호스트에 추가 기능에서 형식을 전달 합니다. 형식이 없습니다. 추가 기능에 대 한 호스트를 이동 하기 때문에이 파이프라인의 추가 기능 측에서 계약 뷰는 어댑터를 포함할 필요가 없습니다.  
  
#### <a name="to-create-the-add-in-side-adapter"></a>추가 기능 측 어댑터를 만들려면  
  
1.  라는 새 프로젝트 추가 `Calc1AddInSideAdapter` 에 `CalculatorV1` 솔루션입니다. 기반으로 **클래스 라이브러리** 템플릿.  
  
2.  **솔루션 탐색기**에 다음 어셈블리에 대 한 참조 추가 `Calc1AddInSideAdapter` 프로젝트:  
  
     탐색기  
  
     System.AddIn.Contract.dll  
  
3.  인접 한 파이프라인 세그먼트에 대 한 프로젝트에 프로젝트 참조를 추가 합니다.  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  각 프로젝트 참조를 선택 및 **속성** 설정 **로컬 복사** 를 **False**합니다. Visual Basic에서 사용 하 여는 **참조** 탭 **프로젝트 속성** 설정 하려면 **로컬 복사** 를 **False** 두 프로젝트 참조에 대 한 합니다.  
  
5.  프로젝트의 기본 클래스의 이름을 바꿉니다 `CalculatorViewToContractAddInSideAdapter`합니다.  
  
6.  클래스 파일에서 네임 스페이스 참조를 추가 <xref:System.AddIn.Pipeline>합니다.  
  
7.  클래스 파일에서 인접 한 세그먼트에 대 한 네임 스페이스 참조 추가: `CalcAddInViews` 및 `CalculatorContracts`합니다. (Visual Basic에서 이러한 네임 스페이스 참조는 `Calc1AddInView.CalcAddInViews` 및 `Calc1Contract.CalculatorContracts`인 Visual Basic 프로젝트에서 기본 네임 스페이스를 해제 했습니다.)  
  
8.  적용 된 <xref:System.AddIn.Pipeline.AddInAdapterAttribute> 특성을 `CalculatorViewToContractAddInSideAdapter` 클래스 추가 기능 측 어댑터로 식별 합니다.  
  
9. 확인는 `CalculatorViewToContractAddInSideAdapter` 클래스 상속 <xref:System.AddIn.Pipeline.ContractBase>의 기본 구현을 제공 하는 <xref:System.AddIn.Contract.IContract> 파이프라인에 대 한 계약 인터페이스를 구현 및 인터페이스를 `ICalc1Contract`합니다.  
  
10. 추가 허용 하는 공용 생성자는 `ICalculator`전용 필드에 캐시 하 고 기본 클래스 생성자를 호출 합니다.  
  
11. 멤버를 구현 하려면 `ICalc1Contract`, 해당 멤버를 호출 하기만 하면는 `ICalculator` 인스턴스 생성자에 전달 되는 결과 반환 합니다. 이 보기에 맞게 변경 (`ICalculator`) 계약 (`ICalc1Contract`).  
  
     다음 코드에서는 완성 된 추가 기능 측 어댑터를 보여 줍니다.  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. 필요에 따라 Visual Studio 솔루션을 빌드하십시오.  
  
## <a name="creating-the-host-side-adapter"></a>호스트 측 어댑터 만들기  
 이 호스트 측 어댑터는 하나의 계약 뷰 구성 됩니다. 이 세그먼트는 계약의 추가 기능 [호스트] 보기에 맞게 변경합니다.  
  
 이 파이프라인에 추가 기능에 서비스를 제공 호스트와 형식 흐름 호스트에 추가 기능에서 합니다. 형식이 없습니다. 추가 기능에 대 한 호스트를 이동 하므로 뷰 계약으로 변환 하는 어댑터를 포함할 필요는 없습니다.  
  
 수명 관리를 구현 하려면 사용을 <xref:System.AddIn.Pipeline.ContractHandle> 계약 수명 토큰을 연결할 개체입니다. 실행 되도록 수명 관리를 위해이 핸들에 대 한 참조를 유지 해야 합니다. 토큰이 적용 되 면 더 이상 사용 되 고 가비지 수집을 사용할 수 있도록 때 추가 기능 시스템 개체의 삭제할 수 있었기 때문에 없는 추가 프로그래밍이 필요 합니다. 자세한 내용은 [수명 관리](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)를 참조하세요.  
  
#### <a name="to-create-the-host-side-adapter"></a>호스트 측 어댑터를 만들려면  
  
1.  라는 새 프로젝트 추가 `Calc1HostSideAdapter` 에 `CalculatorV1` 솔루션입니다. 기반으로 **클래스 라이브러리** 템플릿.  
  
2.  **솔루션 탐색기**에 다음 어셈블리에 대 한 참조 추가 `Calc1HostSideAdapter` 프로젝트:  
  
     탐색기  
  
     System.AddIn.Contract.dll  
  
3.  인접 한 세그먼트에 대 한 프로젝트에 프로젝트 참조를 추가 합니다.  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  각 프로젝트 참조를 선택 및 **속성** 설정 **로컬 복사** 를 **False**합니다. Visual Basic에서 사용 하 여는 **참조** 탭 **프로젝트 속성** 설정 하려면 **로컬 복사** 를 **False** 두 프로젝트 참조에 대 한 합니다.  
  
5.  프로젝트의 기본 클래스의 이름을 바꿉니다 `CalculatorContractToViewHostSideAdapter`합니다.  
  
6.  클래스 파일에서 네임 스페이스 참조를 추가 <xref:System.AddIn.Pipeline>합니다.  
  
7.  클래스 파일에서 인접 한 세그먼트에 대 한 네임 스페이스 참조 추가: `CalcHVAs` 및 `CalculatorContracts`합니다. (Visual Basic에서 이러한 네임 스페이스 참조는 `Calc1HVA.CalcHVAs` 및 `Calc1Contract.CalculatorContracts`인 Visual Basic 프로젝트에서 기본 네임 스페이스를 해제 했습니다.)  
  
8.  적용 된 <xref:System.AddIn.Pipeline.HostAdapterAttribute> 특성을 `CalculatorContractToViewHostSideAdapter` 클래스 호스트 측 어댑터 세그먼트로 식별 합니다.  
  
9. 확인은 `CalculatorContractToViewHostSideAdapter` 추가 기능의 호스트 뷰를 나타내는 인터페이스를 구현 하는 클래스: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` Visual basic에서).  
  
10. 파이프라인 계약 형식을 받는 공용 생성자를 추가 `ICalc1Contract`합니다. 생성자는 계약에 대 한 참조를 캐시 해야 합니다. 만들기 및 새 캐시도 해야 <xref:System.AddIn.Pipeline.ContractHandle> 추가 기능인의 수명을 관리 하는 계약에 대 한 합니다.  
  
    > [!IMPORTANT]
    >  <xref:System.AddIn.Pipeline.ContractHandle> 수명 관리에 중요 합니다. 에 대 한 참조를 유지 하지 못하는 경우는 <xref:System.AddIn.Pipeline.ContractHandle> 개체, 가비지 수집을 회수 합니다 및 프로그램에 필요 하지 않으면 파이프라인 종료 됩니다. 와 같은 진단 하기 어려운 오류가 발생할 수 있습니다이 <xref:System.AppDomainUnloadedException>합니다. 종료는 파이프라인의 정상적인 단계 이므로이 조건은 오류 인지 검색 하기 위해 수명 관리 코드에 대 한 방법은 없습니다.  
  
11. 멤버를 구현 하려면 `ICalculator`, 해당 멤버를 호출 하기만 하면는 `ICalc1Contract` 인스턴스 생성자에 전달 되는 결과 반환 합니다. 이 계약에 맞게 변경 (`ICalc1Contract`) 보기로 (`ICalculator`).  
  
     다음 코드에서는 완성 된 호스트 측 어댑터를 보여 줍니다.  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. 필요에 따라 Visual Studio 솔루션을 빌드하십시오.  
  
## <a name="creating-the-host"></a>호스트 만들기  
 호스트 응용 프로그램 추가 기능에 추가 기능의 호스트 뷰를 통해 상호 작용합니다. 사용 하 여 추가 기능 검색 및 활성화 메서드에서 제공 되는 <xref:System.AddIn.Hosting.AddInStore> 및 <xref:System.AddIn.Hosting.AddInToken> 에서 다음을 수행 하는 클래스:  
  
-   파이프라인 및 추가 기능 정보 캐시를 업데이트 합니다.  
  
-   호스트 보기 유형 추가 기능의 `ICalculator`, 지정 된 파이프라인 루트 디렉터리 아래.  
  
-   사용자는 추가 기능을 사용 하도록 지정 하려면 메시지를 표시 합니다.  
  
-   선택한 추가 기능에 지정 된 보안 신뢰 수준으로 새 응용 프로그램 도메인의 활성화 합니다.  
  
-   사용자 지정 실행 `RunCalculator` 호스트 보기에 지정 된 대로 추가 메서드를 호출 하는 메서드에 합니다.  
  
#### <a name="to-create-the-host"></a>호스트를 만들려면  
  
1.  라는 새 프로젝트 추가 `Calc1Host` 에 `CalculatorV1` 솔루션입니다. 기반으로 **콘솔 응용 프로그램** 템플릿.  
  
2.  **솔루션 탐색기**를 탐색기에 대 한 참조 추가 `Calc1Host` 프로젝트.  
  
3.  에 대 한 프로젝트 참조 추가 `Calc1HVA` 프로젝트. 프로젝트 참조를 선택 및 **속성** 설정 **로컬 복사** 를 **False**합니다. Visual Basic에서 사용 하 여는 **참조** 탭 **프로젝트 속성** 설정 하려면 **로컬 복사** 를 **False**합니다.  
  
4.  클래스 파일 (Visual Basic의 모듈)의 이름을 바꿀 `MathHost1`합니다.  
  
5.  Visual Basic에서 사용 하 여는 **응용 프로그램** 탭은 **프로젝트 속성** 대화 상자를 **시작 개체** 를 **Sub Main**합니다.  
  
6.  클래스 또는 모듈 파일에서 네임 스페이스 참조를 추가 <xref:System.AddIn.Hosting>합니다.  
  
7.  클래스 또는 모듈 파일에서 추가 기능을 [호스트] 보기에 대 한 네임 스페이스 참조 추가: `CalcHVAs`합니다. (Visual basic에서는이 네임 스페이스 참조는 `Calc1HVA.CalcHVAs`인 Visual Basic 프로젝트에서 기본 네임 스페이스를 해제 했습니다.)  
  
8.  **솔루션 탐색기**, 솔루션을 선택 및에서 **프로젝트** 메뉴 선택 **속성**합니다. 에 **솔루션 속성 페이지** 대화 상자, 설정은 **개의 시작 프로젝트** 를이 호스트 응용 프로그램 프로젝트로 합니다.  
  
9. 클래스 또는 모듈 파일에서 사용 하 여는 <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> 메서드 캐시를 업데이트 합니다. 사용 하 여는 <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> 토큰의 컬렉션을 가져오고 사용 하는 메서드는 <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> 메서드를 추가 기능을 활성화 합니다.  
  
     다음 코드에서는 완성 된 호스트 응용 프로그램을 보여 줍니다.  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  이 코드에서는 편의 응용 프로그램 폴더에 있음을 가정 합니다. 에 있는 경우 다른 위치를 설정 하는 코드 줄을 변경 합니다.는 `addInRoot` 변수를 변수에 파이프라인 디렉터리 구조에 대 한 경로 포함 합니다.  
  
     코드를 사용 하 여 한 `ChooseCalculator` 메서드는 토큰을 나열 하 고 추가 기능을 선택 하 라는 메시지입니다. `RunCalculator` 메서드 간단한 수식을 라는 메시지를 사용 하 여 식을 구문 분석 하는 `Parser` 클래스 및 추가 기능에 의해 반환 된 결과 표시 합니다.  
  
10. 필요에 따라 Visual Studio 솔루션을 빌드하십시오.  
  
## <a name="creating-the-add-in"></a>추가 기능 만들기  
 추가 기능에 추가 기능을 보기에서 지정 된 메서드를 구현 합니다. 이 추가 기능을 구현 하는 `Add`, `Subtract`, `Multiply`, 및 `Divide` 작업과 호스트로 결과 반환 합니다.  
  
#### <a name="to-create-the-add-in"></a>추가 기능을 만들려면  
  
1.  라는 새 프로젝트 추가 `AddInCalcV1` 에 `CalculatorV1` 솔루션입니다. 기반으로 **클래스 라이브러리** 템플릿.  
  
2.  **솔루션 탐색기**를 탐색기에 대 한 참조를 프로젝트에 추가 합니다.  
  
3.  에 대 한 프로젝트 참조 추가 `Calc1AddInView` 프로젝트. 프로젝트 참조를 선택 및 **속성**설정, **로컬 복사** 를 **False**합니다. Visual Basic에서 사용 하 여는 **참조** 탭 **프로젝트 속성** 설정 하려면 **로컬 복사** 를 **False** 프로젝트 참조에 대 한 합니다.  
  
4.  클래스의 이름을 `AddInCalcV1`합니다.  
  
5.  클래스 파일에서 네임 스페이스 참조를 추가 <xref:System.AddIn> , 추가 기능을 보기 세그먼트: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` Visual basic에서).  
  
6.  적용 된 <xref:System.AddIn.AddInAttribute> 특성을 `AddInCalcV1` 추가 기능으로 클래스를 식별 하는 클래스인 합니다.  
  
7.  확인는 `AddInCalcV1` 보기 추가 기능을 나타내는 인터페이스를 구현 하는 클래스: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` Visual basic에서).  
  
8.  멤버를 구현 `ICalculator` 적절 한 계산 결과 반환 하 여 합니다.  
  
     다음 코드는 완료 된 추가 기능을 보여 줍니다.  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. 필요에 따라 Visual Studio 솔루션을 빌드하십시오.  
  
## <a name="deploying-the-pipeline"></a>파이프라인 배포  
 이제 빌드하고 필요한 파이프라인 디렉터리 구조에 추가 기능 세그먼트를 배포할 준비가 되었습니다.  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a>파이프라인에 세그먼트를 배포 하려면  
  
1.  솔루션의 각 프로젝트에 대해 사용 하 여는 **빌드** 탭 **프로젝트 속성** (의 **컴파일** Visual Basic의 탭)의 값을 설정는 **출력 경로**  (의 **빌드 출력 경로** Visual basic에서). 응용 프로그램 폴더 이름을 지정 하는 경우 `MyApp`을 다음 폴더에 프로젝트를 빌드하는 것 등.  
  
    |프로젝트|Path|  
    |-------------|----------|  
    |AddInCalcV1|MyApp\Pipeline\AddIns\CalcV1|  
    |Calc1AddInSideAdapter|MyApp\Pipeline\AddInSideAdapters|  
    |Calc1AddInView|MyApp\Pipeline\AddInViews|  
    |Calc1Contract|MyApp\Pipeline\Contracts|  
    |Calc1Host|MyApp|  
    |Calc1HostSideAdapter|MyApp\Pipeline\HostSideAdapters|  
    |Calc1HVA|MyApp|  
  
    > [!NOTE]
    >  응용 프로그램 폴더 이외의 위치에 파이프라인 폴더 구조를 결정 한 경우 그에 따라 테이블에 표시 된 경로 수정 해야 합니다. 디렉터리 요구 사항에 파이프라인의 설명을 참조 [파이프라인 개발 요구 사항](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)합니다.  
  
2.  Visual Studio 솔루션을 빌드합니다.  
  
3.  어셈블리는 올바른 디렉터리에 복사 된 어셈블리의 추가 복사본이 된 잘못 된 폴더에 설치 되어 있는지 확인 하려면 응용 프로그램 및 파이프라인 디렉터리를 확인 합니다.  
  
    > [!NOTE]
    >  변경 되지 않은 경우 **로컬 복사** 를 **False** 에 대 한는 `Calc1AddInView` 프로젝트 참조에는 `AddInCalcV1` 프로젝트 로더 컨텍스트 문제에서 하지 것입니다 추가 기능에 있는 것입니다.  
  
     파이프라인에 배포 하는 방법에 대 한 정보를 참조 하십시오. [파이프라인 개발 요구 사항](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)합니다.  
  
## <a name="running-the-host-application"></a>호스트 응용 프로그램 실행  
 이제 호스트를 실행 하 고 추가 기능을 상호 작용할 준비가 되었습니다.  
  
#### <a name="to-run-the-host-application"></a>호스트 응용 프로그램을 실행 하려면  
  
1.  명령 프롬프트에서 응용 프로그램 디렉터리로 이동 하 고 호스트 응용 프로그램을 실행 `Calc1Host.exe`합니다.  
  
2.  호스트 사용 가능한 추가 기능을 모두 찾습니다 해당 형식의 추가 기능을 선택 하 라는 메시지가 표시 됩니다. 입력 **1** 에 사용할 수 있는 추가 기능에 대 한 합니다.  
  
3.  와 같은 계산기 수식을 입력 **2 + 2**합니다. 숫자 및 연산자 사이 공백이 없어야 합니다.  
  
4.  형식 **종료** 누릅니다는 **Enter** 키를 응용 프로그램을 닫습니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 호스트 변경으로 이전 버전과 호환성을 사용 하도록 설정](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [연습: 호스트와 추가 기능 간에 컬렉션 전달](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [파이프라인 개발 요구 사항](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [계약, 뷰 및 어댑터](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [Pipeline Development](../../../docs/framework/add-ins/pipeline-development.md)
