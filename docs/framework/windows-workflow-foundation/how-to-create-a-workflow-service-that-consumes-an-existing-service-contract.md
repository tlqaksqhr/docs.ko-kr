---
title: "방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 11d11b59-acc4-48bf-8e4b-e97b516aa0a9
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 방법: 기존 서비스 계약을 사용하는 워크플로 서비스 만들기
[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]는 계약 중심 워크플로 개발의 형태로 웹 서비스와 워크플로 간에 보다 우수한 통합 성능을 제공합니다.계약 중심 워크플로 개발 도구를 사용하면 코드에서 계약을 먼저 디자인할 수 있습니다.그러면 이 도구는 계약의 작업을 위해 도구 상자에 활동 템플릿을 자동으로 생성합니다.  
  
> [!NOTE]
>  이 항목에서는 계약 중심 워크플로 서비스를 만들기 위한 단계별 지침을 제공합니다.계약 중심 워크플로 서비스 개발[!INCLUDE[crabout](../../../includes/crabout-md.md)][계약 중심 워크플로 서비스 개발](../../../docs/framework/windows-workflow-foundation//contract-first-workflow-service-development.md)을 참조하십시오.  
  
### 워크플로 프로젝트 만들기  
  
1.  [!INCLUDE[vs_current_short](../../../includes/vs-current-short-md.md)]에서 **파일**, **새 프로젝트**를 차례로 선택합니다.**템플릿** 트리의 **C\#** 노드에서 **WCF** 노드를 선택하고 **WCF 워크플로 서비스 응용 프로그램** 템플릿을 선택합니다.  
  
2.  새 프로젝트의 이름을 `ContractFirst`로 지정하고 **확인**을 클릭합니다.  
  
### 서비스 계약 만들기  
  
1.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가**, **새 항목…**을 차례로 선택합니다.왼쪽의 **코드** 노드를 선택하고 오른쪽의 **클래스** 템플릿을 선택합니다.새 클래스의 이름을 `IBookService`로 지정하고 **확인**을 클릭합니다.  
  
2.  표시되는 코드 창의 맨 위에서 `System.Servicemodel`에 Using 문을 추가합니다.  
  
    ```  
    using System.ServiceModel;  
    ```  
  
3.  샘플 클래스 정의를 다음과 같은 인터페이스 정의로 변경합니다.  
  
    ```  
    [ServiceContract]  
        public interface IBookService  
        {  
            [OperationContract]  
            void Buy(string bookName);  
  
            [OperationContract(IsOneWay=true)]  
            void Checkout();  
        }  
    ```  
  
4.  **Ctrl\+Shift\+B**를 눌러 프로젝트를 빌드합니다.  
  
### 서비스 계약 가져오기  
  
1.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **서비스 계약 가져오기**를 선택합니다.**\<현재 프로젝트\>**에서 모든 하위 노드를 열고 **IBookService**를 선택합니다.**확인**을 클릭합니다.  
  
2.  작업이 성공적으로 완료되었음을 알리는 대화 상자가 열리고 프로젝트가 빌드된 후 생성된 활동이 도구 상자에 나타납니다.**확인**을 클릭합니다.  
  
3.  가져온 활동이 도구 상자에 표시되도록 **Ctrl\+Shift\+B**를 눌러 프로젝트를 빌드합니다.  
  
4.  **솔루션 탐색기**에서 Service1.xamlx를 엽니다.워크플로 서비스가 디자이너에 표시됩니다.  
  
5.  **Sequence** 활동을 선택합니다.속성 창에서 **ImplementedContract** 속성에 있는 **…** 단추를 클릭합니다.표시되는 **형식 컬렉션 편집기** 창에서 **형식** 드롭다운을 클릭하고 **형식 찾아보기…** 항목을 선택합니다.**.Net 형식 찾아보기 및 선택** 대화 상자의 **\<현재 프로젝트\>** 아래에서 모든 하위 노드를 열고 **IBookService**를 선택합니다.**확인**을 클릭합니다.**형식 컬렉션 편집기** 대화 상자에서 **확인**을 클릭합니다.  
  
6.  **ReceiveRequest** 및 **SendResponse** 활동을 선택하고 삭제합니다.  
  
7.  도구 상자에서 **Buy\_ReceiveAndSendReply** 및 **Checkout\_Receive** 활동을 **Sequential Service** 활동으로 끌어 옵니다.