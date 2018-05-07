---
title: UriTemplate 테이블 샘플
ms.date: 03/30/2017
ms.assetid: 5dd1d38f-1989-4c64-820d-821f5a02216a
ms.openlocfilehash: ef445e30257e9bf99e111c1a1f569e42c2017b56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="uritemplate-table-sample"></a>UriTemplate 테이블 샘플
<xref:System.UriTemplateTable> 클래스는 `UriTemplate` 인스턴스 집합으로 작업할 수 있도록 사전과 비슷한 연결 테이블 구조체를 제공합니다. 특정 URI(Uniform Resource Identifier)를 테이블의 모든 템플릿에 대해 효율적으로 일치시킬 수 있으며 일치한 템플릿과 연결된 데이터를 검색할 수 있습니다.  
  
 이 샘플에서는 `UriTemplateTable` 클래스와 관련된 다음 주요 개념을 보여 줍니다.  
  
-   `UriTemplateTable`을 인스턴스화하는 구문  
  
-   `UriTemplateTable`을 키/값 쌍의 집합으로 채우기  
  
-   <xref:System.UriTemplateTable.MatchSingle%2A>을 사용하여 후보 URI를 테이블과 일치시키기  
  
### <a name="to-set-up-build-and-run-the-sample"></a>샘플을 설치, 빌드 및 실행하려면  
  
1.  C# 또는 Visual Basic .NET 버전의 솔루션을 빌드하려면 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)의 지침을 따릅니다.  
  
2.  지침에 따라 단일 또는 다중 컴퓨터 구성에서 샘플을 실행 하려면 [Windows Communication Foundation 샘플 실행](../../../../docs/framework/wcf/samples/running-the-samples.md)합니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가로 이동 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](http://go.microsoft.com/fwlink/?LinkId=150780) 모든 Windows Communication Foundation (WCF)를 다운로드 하 고 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Web\UriTemplateTable`  
  
## <a name="see-also"></a>참고 항목  
 [UriTemplate 테이블 디스패처](../../../../docs/framework/wcf/samples/uritemplate-table-dispatcher-sample.md)  
 [UriTemplate](../../../../docs/framework/wcf/samples/uritemplate-sample.md)
