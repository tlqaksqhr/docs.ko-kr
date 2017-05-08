---
title: "&lt;commonParameters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ffc20832-34d6-4622-8174-81924fd53514
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# &lt;commonParameters&gt;
여러 서비스에서 전역적으로 사용되는 매개 변수의 컬렉션을 나타냅니다.  일반적으로 이 컬렉션에는 영속 서비스에서 공유할 수 있는 데이터베이스 연결 문자열이 포함됩니다.  
  
## 구문  
  
```  
  
<workflowRuntime>  
   <commonParameters>  
      <add name="String" value="String" />  
   </commonParameters>  
</workflowRuntime>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)|서비스에서 사용되는 일반 매개 변수의 이름\-값 쌍을 컬렉션에 추가합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[\<workflowRuntime\>](../../../../../docs/framework/configure-apps/file-schema/wcf/workflowruntime.md)|워크플로 기반 [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] 서비스를 호스트하기 위해 <xref:System.Workflow.Runtime.WorkflowRuntime>의 인스턴스에 대한 설정을 지정합니다.|  
  
## 설명  
 `<commonParameters>` 요소는 여러 서비스에서 전역적으로 사용되는 모든 매개 변수를 정의합니다. 예를 들어 <xref:System.Workflow.Runtime.Hosting.SharedConnectionWorkflowCommitWorkBatchService>를 사용하는 경우 `ConnectionString`을 정의합니다.  
  
> [!NOTE]
>  SQL 추적 서비스에서는 `ConnectionString` 값이 `<commonParameters>` 섹션에 지정된 경우 해당 값을 일관성 있게 사용하지 않습니다.  `StateMachineWorkflowInstance.StateHistory` 속성을 검색하는 것과 같은 일부 작업이 실패할 수 있습니다.  이 문제를 해결하려면 다음 예제와 같이 추적 공급자에 대한 구성 섹션에 `ConnectionString` 특성을 지정하세요.  
  
 `<add`  
  
 `type="System.Workflow.Runtime.Tracking.SqlTrackingService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35"`  
  
 `ConnectionString="Data Source=localhost;Initial Catalog=Partner20WFTP;Integrated Security=True;" />`  
  
 작업 일괄 처리를 지속성 저장소에 커밋하는 서비스\(예: <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService> 및 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>\)의 경우 다음 예제와 같이 `EnableRetries` 매개 변수를 사용하여 트랜잭션을 다시 시도하도록 할 수 있습니다.  
  
```  
<WorkflowRuntime Name="SampleApplication" UnloadOnIdle="false">  
    <commonParameters>  
        <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;" />  
        <add name="EnableRetries" value="True" />  
    </commonParameters>  
    <Services>  
        <add type="System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService, System.Workflow.Runtime, Version=3.0.00000.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" EnableRetries="False" />   
     </Services>  
</WorkflowRuntime>  
```  
  
 `EnableRetries` 매개 변수는 전역 수준에서 설정하거나\(*CommonParameters* 섹션\) `EnableRetries`를 지원하는 개별 서비스에 대해 설정할 수 있습니다\(*Services* 섹션\).  
  
 다음 샘플 코드에서는 일반 매개 변수를 프로그래밍 방식으로 변경하는 방법을 보여 줍니다.  
  
```  
Configuration config=WebConfigurationManager.OpenWebConfiguration("/Workflow", "Default Web Site", null, "localhost");  
WorkflowRuntimeSection wfruntime=config.GetSection("WorkflowRuntime") as WorkflowRuntimeSection;  
NameValueConfigurationCollection commonParameters=wfruntime.CommonParameters;  
commonParameters["ConnectionString"].Value="another connection string";  
config.Save();  
```  
  
 Windows Workflow Foundation 호스트 응용 프로그램의 <xref:System.Workflow.Runtime.WorkflowRuntime> 개체의 동작을 제어할 수 있는 구성 파일을 사용하는 방법은 [Workflow Configuration Files](http://msdn.microsoft.com/ko-kr/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)을 참조하세요.  
  
## 예제  
  
```  
<commonParameters>  
   <add name="ConnectionString" value="Initial Catalog=WorkflowStore;Data Source=localhost;Integrated Security=SSPI;"/>  
   <add name="EnableRetries" value="true"/>  
</commonParameters>  
```  
  
## 참고 항목  
 <xref:System.ServiceModel.Configuration.WorkflowRuntimeElement>   
 <xref:System.Workflow.Runtime.Configuration.WorkflowRuntimeServiceElement>   
 <xref:System.Workflow.Runtime.WorkflowRuntime>   
 <xref:System.Workflow.Runtime.Hosting.DefaultWorkflowCommitWorkBatchService>   
 <xref:System.Workflow.Runtime.Hosting.SqlWorkflowPersistenceService>   
 [Workflow Configuration Files](http://msdn.microsoft.com/ko-kr/ada4bb90-6c9d-4f3d-a9d0-b559bb0f9909)   
 [\<add\>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-commonparameters.md)