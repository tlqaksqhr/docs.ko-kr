---
title: "속성 승격 활동"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bd8356927ad7cb4c24cc278fcb901cc543c6d7b5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="property-promotion-activity"></a>속성 승격 활동
이 샘플에서는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 승격 기능을 워크플로 작성 환경에 직접 통합하는 종단 간 솔루션을 제공합니다. 승격 기능의 사용을 단순화하는 워크플로 확장, 워크플로 활동 및 구성 요소의 컬렉션이 제공됩니다. 또한 샘플에는 이 컬렉션을 사용하는 방법을 보여 주는 간단한 워크플로가 포함되어 있습니다.  
  
> [!NOTE]
>  예제는 교육용으로만 제공되므로 프로덕션 환경에서 사용하기에 적합하지 않으며 프로덕션 환경에서 테스트되지 않았습니다. Microsoft에서는 이러한 샘플에 대해 기술 지원을 제공하지 않습니다.  
  
## <a name="prerequisites"></a>필수 조건  
  
-   초기화된 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 데이터베이스  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## <a name="sample-projects"></a>샘플 프로젝트  
  
-   **PropertyPromotionActivity** 프로젝트에는 승격 관련 구성 요소, 워크플로 활동 및 워크플로 확장에 파일이 포함 되어 있습니다.  
  
-   **CounterServiceApplication** 프로젝트를 사용 하는 샘플 워크플로가 포함 되어는 **SqlWorkflowInstanceStorePromotion** 프로젝트.  
  
-   <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 데이터베이스에 대해 실행되어야 하는 SQL 스크립트(PropertyPromotionActivitySQLSample.sql)  
  
-   두 가지 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 프로젝트를 연결하는 솔루션 파일(`PropertyPromotionActivity.sln`)  
  
## <a name="to-set-up-and-run-the-sample"></a>샘플을 설치하고 실행하려면  
  
1.  워크플로 지속성 데이터베이스를 초기화합니다.  
  
    1.  샘플 디렉터리(\WF\Basic\Persistence\PropertyPromotionActivity)로 이동하고 CreateInstanceStore.cmd를 실행합니다.  
  
    2.  관리자 권한이 없는 경우 SQL Server 로그인을 만듭니다. SQL Server Management Studio에서로 이동 **보안**, **로그인**합니다. 마우스 오른쪽 단추로 클릭 **로그인** 새 로그인을 만듭니다. SQL 역할을 열어 ACL 사용자를 추가 **데이터베이스**, **InstanceStore**, **보안**합니다. 마우스 오른쪽 단추로 클릭 **사용자** 선택 **새 사용자**합니다. 설정의 **로그인 이름** 위에서 만든 사용자에 게 합니다. 데이터베이스 역할 멤버 자격(예: System.Activities.DurableInstancing.InstanceStoreUsers)에 사용자를 추가합니다. 사용자가 이미 있을 수도 있습니다(예: 사용자 dbo).  
  
2.  [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]에서 PropertyPromotionActivity.sln 솔루션 파일을 엽니다.  
  
3.  SQL Server Express의 로컬 설치가 아닌 데이터베이스에 인스턴스 저장소를 만든 경우 데이터베이스 연결 문자열을 업데이트해야 합니다. App.config 파일을 변경는 **CounterServiceApplication** 의 값을 설정 하 여는 `connectionString` 특성에 `sqlWorkflowInstanceStorePromotion` 노드 초기화 된 지 속성 데이터베이스를 가리키도록 1 단계에서 합니다.  
  
4.  솔루션을 빌드하고 실행합니다. Counter WF 서비스가 시작되고 워크플로 인스턴스가 자동으로 시작됩니다.  
  
5.  지속성 데이터베이스의 [dbo].[CounterService] 뷰에서 모든 행을 빠르게 선택합니다. 이 뷰는 1단계에서 CreateInstanceStore.cmd를 실행하여 추가되었습니다. 다음과 유사한 결과 집합이 표시됩니다.  
  
    |InstanceId|CounterValue|CounterValueLastUpdated|  
    |----------------|------------------|-----------------------------|  
    |2FA2C302-929E-4C0D-8C25-768A3DA20CE5|12|2010-02-18 22:48:01.740|  
  
     뷰를 계속 새로 고치면 CounterValue와 CounterValueLastUpdated가 2초마다 변경됩니다. 이 간격마다 카운터가 자동으로 업데이트됩니다. CounterValue와 CounterValueLastUpdated는 이 워크플로의 승격된 속성을 나타냅니다.  
  
## <a name="to-remove-the-sample"></a>샘플을 제거하려면  
  
-   샘플 디렉터리(\WF\Basic\Persistence\PropertyPromotionActivity)에서 RemoveInstanceStore.cmd를 실행합니다.  
  
## <a name="understanding-this-sample"></a>이 샘플 이해  
 이 샘플에는 두 가지 프로젝트와 SQL 파일이 포함되어 있습니다.  
  
-   **CounterServiceApplication** 간단한 Counter WF 서비스를 호스트 하는 콘솔 응용 프로그램입니다. `Start` 끝점을 통해 단방향 메시지를 받을 때 워크플로는 0부터 29까지 계산하며 2초마다 카운터 변수를 증가시킵니다. 각 카운터가 증가한 후 워크플로가 유지되고 승격된 속성이 [dbo].[CounterService] 뷰에서 업데이트됩니다. 콘솔 응용 프로그램은 실행될 때 WF 서비스를 호스트하고 메시지를 `Start` 끝점에 보내 Counter WF 인스턴스를 만듭니다.  
  
-   **PropertyPromotionActivity** 워크플로 확장명, 워크플로 활동 및 구성 요소를 포함 하는 클래스 라이브러리는 **CounterServiceApplication** 사용 합니다.  
  
-   **PropertyPromotionActivitySQLSample.sql** 만들고 추가 보기 [dbo]. [ CounterService] 데이터베이스에 있습니다.  
  
### <a name="counterserviceapplication"></a>CounterServiceApplication  
  
#### <a name="using-the-sqlworkflowinstancestorepromotion-configuration-element"></a>SqlWorkflowInstanceStorePromotion 구성 요소 사용  
 `SqlWorkflowInstanceStorePromotion` 구성 요소는 `SqlWorkflowInstanceStore` 구성 요소에서 상속하지만 `promotionSets`라는 추가 구성 요소를 추가합니다. `promotionSets` 요소를 사용하여 구성을 통해 승격된 속성을 지정할 수 있습니다. 이는 샘플에서 사용되는 구성 파일입니다.  
  
```xml  
<sqlWorkflowInstanceStorePromotion connectionString ="Data Source=.;Initial Catalog=SqlWorkflowInstanceStoreTest;Integrated Security=True;">  
  <promotionSets>  
    <promotionSet name="CounterService">  
      <promotedValue propertyName="Count"/>  
      <promotedValue propertyName="LastIncrementedAt"/>  
    </promotionSet>  
  </promotionSets>  
</sqlWorkflowInstanceStorePromotion>  
```  
  
 [dbo].[CounterService] 뷰의 정의를 검사합니다.  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
```  
  
 워크플로 인스턴스가 유지될 때 구성에 정의된 각 `InstancePromotedProperties`의 `PromotionSet` 뷰에 행이 삽입됩니다. 이 행에는 `PromotionSet`의 승격된 속성이 모두 포함되어 있습니다(열당 하나의 승격된 속성). 이 `PromotionSet`는 `InstanceId, PromotionName` 튜플로 키가 지정됩니다. 이 샘플에서는 이름 특성이 `PromotionSet`인 `CounterService` 하나가 구성에 정의되어 있습니다. `PromotionName` 열 값은 `PromotionSet` 요소의 이름 특성과 같습니다.  
  
 `promotedValue` 요소의 순서는 `InstancePromotedProperties` 뷰에서 승격된 속성의 배치와 관련됩니다. `Count`는 첫 번째 `promotedValue` 요소입니다. `Value1` 뷰의 `InstancePromotedProperties` 열에 매핑됩니다. `LastIncrementedAt`는 두 번째 `promotedValue` 요소입니다. `Value2` 뷰의 `InstancePromotedProperties` 열에 매핑됩니다.  
  
#### <a name="using-the-promotevalue-activity"></a>PromoteValue 활동 사용  
 [!INCLUDE[wf2](../../../../includes/wf2-md.md)] Designer에서 CounterService.xamlx 파일을 검사합니다. WF 정의에는 `PromoteValue<DateTime>` 및 `PromoteValue<Int32>`라는 두 가지 특수 활동이 있습니다.  
  
 `PromoteValue<Int32>` 활동의 `Name` 멤버는 `Count`으로 정의됩니다. 이는 구성의 첫 번째 `promotedValue` 요소와 일치하며 `Value`가 `Counter` 워크플로 변수로 정의됩니다. 워크플로가 유지될 때 `Counter` 워크플로 변수는 `Value1` 뷰의 `InstancePromotedProperties` 열에 승격된 속성으로 유지됩니다.  
  
 `PromoteValue<DateTime>` 활동의 `Name` 멤버는 `LastIncrementedAt`으로 정의됩니다. 이는 구성의 두 번째 `promotedValue` 요소와 일치하며 `Value`가 `TimeLastIncremented` 워크플로 변수로 정의됩니다. 즉, 워크플로가 유지될 때 `TimeLastIncremented` 워크플로 변수의 값은 `Value2` 뷰의 `InstancePromotedProperties` 열에 승격된 속성으로 유지됩니다.  
  
 `PromotedValue` 활동에는 `ClearExistingPromotedData`라는 부울 멤버도 있습니다. 이 멤버가 `true`로 설정되면 워크플로의 해당 지점까지 승격된 속성 값이 모두 지워집니다. 예를 들어 Sequence 활동이 다음과 같이 정의된 경우  
  
1.  PromoteValue {Name = "Count", 값 = 3을 (를)  
  
2.  PromoteValue {이름 값 "LastIncrementedAt" = = 1-1-2000}  
  
3.  유지  
  
4.  PromoteValue {Name = "Count", 값 = 4, ClearExistingPromotedData = true}  
  
5.  유지  
  
 두 번째 유지에서 `Count`의 승격된 값은 4입니다. 그러나 승격 된 값에 대 한 `LastIncrementedAt` 됩니다 `NULL`합니다. 4단계에서 `ClearExistingPromotedData`가 `true`로 설정되지 않은 경우 두 번째 유지 후에 Count의 승격된 값은 4입니다. 이에 따라 `LastIncrementedAt`의 승격된 값은 여전히 1-1-2000입니다.  
  
### <a name="propertypromotionactivity"></a>PropertyPromotionActivity  
 이 클래스 라이브러리에는 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 승격 기능의 사용을 단순화하는 다음 공용 클래스가 포함되어 있습니다.  
  
#### <a name="promotevalue-class"></a>PromoteValue 클래스  
 이 클래스는 한 속성을 승격합니다. 승격된 속성의 이름은 구성에 있는 `promotedValue` 요소의 이름 특성과 일치해야 합니다. 이 활동은 Workflow Designer에서 사용할 수 있습니다. 사용 예를 보려면 CounterServiceApplication을 참조하세요.  
  
```csharp  
public class PromoteValue<T> : CodeActivity  
{  
    public PromoteValue()  
    {  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public string Name { get; set; }  
    public InArgument<T> Value { get; set; }  
}  
```  
  
 ClearExistingPromotedData(Bool)  
 이 활동 전에 승격된 모든 값을 지웁니다.  
  
 Name(string)  
 이 속성을 나타내는 이름입니다. 이름 특성을 일치 해야이 \<promotedValue >는 구성 요소입니다.  
  
 값 (InArgument\<T >)  
 열에 저장할 변수/값입니다.  
  
#### <a name="promotevalues-class"></a>PromoteValues 클래스  
 여러 속성을 승격합니다. 승격된 속성의 이름은 구성에 있는 `promotedValue` 요소의 모든 이름 특성과 일치해야 합니다. `PromoteValue` 활동과 유사하게 사용할 수 있지만 여러 속성을 동시에 승격할 수 있다는 점이 다릅니다. 이 활동은 Workflow Designer에서 사용할 수 없습니다.  
  
```  
public class PromoteValues : CodeActivity  
{  
    public PromoteValues()  
    {  
        this.ValuesToPromote = new Dictionary<string, InArgument>();  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public IDictionary<string, InArgument> ValuesToPromote { get; set; }  
}  
```  
  
#### <a name="sqlworkflowinstancestorepromotionbehavior"></a>SqlWorkflowInstanceStorePromotionBehavior  
 `SqlWorkflowInstanceStoreBehavior`에서 파생됩니다. 이 파생 클래스는 사용자 지정 지속성 참가자(이 라이브러리의 일부이기도 함)를 워크플로 확장으로 추가합니다. 이전의 두 가지 워크플로 활동의 구현은 이 사용자 지정 지속성 참가자에 의존합니다.  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
```  
  
 이 클래스 라이브러리에는 이전의 승격 활동에서 사용되는 사용자 지정 지속성 참가자와 `ConfigurationElement`에 대한 `SqlWorkflowInstanceStorePromotionElement` 구현도 포함되어 있습니다.  
  
### <a name="propertypromotionactivitysqlsample"></a>PropertyPromotionActivitySQLSample  
 이 SQL 파일에서는 CounterService 승격이 설정된 모든 인스턴스를 쿼리하기 위한 `[dbo].[CounterService]` 뷰뿐만 아니라 `[InstancePromotedProperties]` 뷰도 만듭니다.  
  
> [!IMPORTANT]
>  컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다. 계속하기 전에 다음(기본) 디렉터리를 확인하세요.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  이 디렉터리가 없으면 [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4(.NET Framework 4용 WCF(Windows Communication Foundation) 및 WF(Windows Workflow Foundation) 샘플)](http://go.microsoft.com/fwlink/?LinkId=150780) 로 이동하여 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 모두 다운로드하세요. 이 샘플은 다음 디렉터리에 있습니다.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## <a name="see-also"></a>참고 항목  
 [AppFabric 호스팅 및 지 속성 샘플](http://go.microsoft.com/fwlink/?LinkId=193961)
