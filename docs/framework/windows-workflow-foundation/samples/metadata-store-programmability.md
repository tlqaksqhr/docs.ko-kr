---
title: 메타데이터 저장소 프로그래밍 기능
ms.date: 03/30/2017
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
ms.openlocfilehash: 6efcb86e29f19a29d6ef382afa336d0ca2ce4306
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33517439"
---
# <a name="metadata-store-programmability"></a>메타데이터 저장소 프로그래밍 기능
메타데이터 저장소는 CLR 특성 형식의 임의의 메타데이터를 런타임에 형식에 연결할 수 있는 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 기능입니다. 이를 통해 런타임 구성 요소와 해당 디자인 타임 구성 요소 간의 느슨한 결합이 가능할 뿐 아니라 런타임에 영향을 주지 않고 디자인 타임 구성 요소를 변경할 수 있습니다. 이 샘플에서는 제어 권한이 없는 소스인 런타임 형식에 특성을 적용하여 메타데이터 저장소를 기반으로 프로그래밍하는 방법을 보여 줍니다. 즉, 호스팅 응용 프로그램이 형식 집합에 대한 메타데이터를 등록하는 방법을 보여 줍니다.  
  
 출력에 예기치 않은 추가 특성인, 없는데 <!--zz <xref:System.Runtime.InteropServices.GUIDAttribute> --> `System.Runtime.InteropServices.GUIDAttribute`합니다. 이 특성은 메타데이터 API를 사용할 때 추가되며 샘플 실행에는 영향을 주지 않습니다.  
  
 이 샘플에서는 다음 작업을 수행하는 방법을 보여 줍니다.  
  
## <a name="demonstrates"></a>세부 항목  
  
-   메타데이터 저장소 API를 사용하여 특성 삽입  
  
-   콜백 메커니즘을 사용하여 메타데이터 등록 지연  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 ProgrammingMetadataStore.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`