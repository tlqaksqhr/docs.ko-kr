---
title: "활동 지역화 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8ee7bc16-e609-469a-a3e8-8062952e2676
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# 활동 지역화
워크플로 응용 프로그램 및 구성 요소가 다른 문화권과 언어로 지역화될 가능성이 있는 경우 다시 컴파일하지 않고 지역화할 수 있도록 리소스 문자열을 사용해야 합니다.  
  
## 활동 지역화  
 지역화해야 하는\(다른 언어와 문화권에 대해 다른 버전으로 릴리스해야 하는\) 모든 응용 프로그램에서 사용자에게 표시되는 문자열은 코드에 직접 넣지 말고 리소스 파일에 저장해야 합니다.그러면 <xref:System.Environment.GetResourceString>을 통해 문자열에 액세스할 수 있습니다.여러 언어로 배포되는 구성 요소를 개발하는 경우 활동 유효성 검사 메시지, 사용자 정의 추적 데이터, 추적 메시지 및 오류 메시지에도 리소스 문자열을 사용할 수 있습니다.  
  
 다음 연습에서는 리소스 파일을 사용하는 방법을 보여 줍니다.  
  
#### 지역화되는 문자열에 리소스 파일 사용  
  
1.  [!INCLUDE[vs2010](../../../includes/vs2010-md.md)]의 **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가…**, **새 항목…**을 차례로 선택합니다.  
  
2.  **리소스 파일**을 선택하고 파일 이름을 ErrorResources.resx로 지정합니다.**추가**를 클릭합니다.  
  
3.  리소스 파일을 엽니다.**이름**을 ErrorString으로 지정하고 **값**을 "The activity is not valid"로 지정하여 새 항목을 추가합니다.  
  
4.  클래스에 다음 `using` 문을 추가합니다.  
  
    ```  
    using System.Reflection;  
    using System.Resources;  
  
    ```  
  
5.  프로젝트에서 리소스 관리자를 만듭니다.  
  
    ```  
    ResourceManager ErrorManager;  
    ...  
    ErrorManager = new ResourceManager("MyNamespace.ErrorResources", Assembly.GetExecutingAssembly());  
  
    ```  
  
6.  필요한 경우 리소스 관리자에서 문자열을 가져옵니다.  
  
    ```  
    String errorMessage = ErrorManager.GetString("ErrorString");  
  
    ```  
  
 다음 코드 샘플에서는 <xref:System.Activities.Activity.CacheMetadata%2A> 메서드에서 지역화되는 문자열을 사용하는 방법을 보여 줍니다.  
  
```  
       protected override void CacheMetadata(CodeActivityMetadata metadata)  
        {  
           .....  
          // rest of the code elided for brevity  
           .....  
            if (this.Value != null && this.To != null)  
            {  
                if (!TypeHelper.AreTypesCompatible(this.Value.ArgumentType, this.To.ArgumentType))  
                {  
//---------------------------------------------  
// ** SR.TypeMismatchForAssign will fetch the string from the resource manager **  
//---------------------------------------------  
                    metadata.AddValidationError(SR.TypeMismatchForAssign(  
                                this.Value.ArgumentType,  
                                this.To.ArgumentType,  
                                this.DisplayName));  
                }  
            }  
        }  
```