---
title: "메타데이터 저장소 프로그래밍 기능 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5b613661-f3f9-4e07-8e88-28c9ea2fd8f8
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# 메타데이터 저장소 프로그래밍 기능
메타데이터 저장소는 CLR 특성 형식의 임의의 메타데이터를 런타임에 형식에 연결할 수 있는 [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] 기능입니다.이를 통해 런타임 구성 요소와 해당 디자인 타임 구성 요소 간의 느슨한 결합이 가능할 뿐 아니라 런타임에 영향을 주지 않고 디자인 타임 구성 요소를 변경할 수 있습니다.이 샘플에서는 제어 권한이 없는 소스인 런타임 형식에 특성을 적용하여 메타데이터 저장소를 기반으로 프로그래밍하는 방법을 보여 줍니다.즉, 호스팅 응용 프로그램이 형식 집합에 대한 메타데이터를 등록하는 방법을 보여 줍니다.  
  
 출력에는 예기치 않은 추가 특성인 <xref:System.Runtime.InteropServices.GUIDAttribute>가 있을 수 있습니다.이 특성은 메타데이터 API를 사용할 때 추가되며 샘플 실행에는 영향을 주지 않습니다.  
  
 이 샘플에서는 다음 작업을 수행하는 방법을 보여 줍니다.  
  
## 세부 항목  
  
-   메타데이터 저장소 API를 사용하여 특성 삽입  
  
-   콜백 메커니즘을 사용하여 메타데이터 등록 지연  
  
#### 샘플을 설치, 빌드 및 실행하려면  
  
1.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]을 사용하여 ProgrammingMetadataStore.sln 솔루션 파일을 엽니다.  
  
2.  Ctrl\+Shift\+B를 눌러 솔루션을 빌드합니다.  
  
3.  F5 키를 눌러 솔루션을 실행합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.계속하기 전에 다음\(기본\) 디렉터리를 확인하십시오.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation \(WCF\) and Windows Workflow Foundation \(WF\) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780)로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하십시오.이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\MetadataStore`  
  
## 참고 항목