---
title: "방법: My 네임스페이스 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "C# 언어, My 네임스페이스 액세스"
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# 방법: My 네임스페이스 사용(C# 프로그래밍 가이드)
<xref:Microsoft.VisualBasic.MyServices> 네임스페이스\(Visual Basic의 경우 `My`\)를 사용하여 많은 .NET Framework 클래스에 간편하고 직관적으로 액세스할 수 있으며, 이를 통해 컴퓨터, 응용 프로그램, 설정, 리소스 등과 상호 작용하는 코드를 작성할 수 있습니다.  `MyServices` 네임스페이스는 원래 Visual Basic에서 사용하도록 디자인되었지만 C\# 응용 프로그램에서도 사용할 수 있습니다.  
  
 Visual Basic에서 `MyServices` 네임스페이스를 사용하는 방법에 대한 자세한 내용은 [Development with My](../../../visual-basic/developing-apps/development-with-my/index.md)을 참조하십시오.  
  
## 참조 추가  
 솔루션에서 `MyServices` 클래스를 사용하려면 우선 Visual Basic 라이브러리에 대한 참조를 추가해야 합니다.  
  
#### Visual Basic 라이브러리에 대한 참조를 추가하려면  
  
1.  **솔루션 탐색기**에서 **참조** 노드를 마우스 오른쪽 단추로 클릭하고 **참조 추가**를 선택합니다.  
  
2.  **참조** 대화 상자가 표시되면 목록을 아래로 스크롤하여 Microsoft.VisualBasic.dll을 선택합니다.  
  
     또한 프로그램 시작 부분의 `using` 섹션에 다음 줄을 추가해야 합니다.  
  
     [!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces3.cs#18)]  
  
## 예제  
 다음 예제에서는 `MyServices` 네임스페이스에 있는 여러 정적 메서드를 호출합니다.  이 코드를 컴파일하려면 프로젝트에 Microsoft.VisualBasic.DLL에 대한 참조를 추가해야 합니다.  
  
 [!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces3.cs#19)]  
  
 C\# 응용 프로그램에서 `MyServices` 네임스페이스에 있는 모든 클래스를 호출할 수 있는 것은 아닙니다. 예를 들어 <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> 클래스는 호환되지 않습니다.  이 경우에는 VisualBasic.dll에도 포함된 <xref:Microsoft.VisualBasic.FileIO.FileSystem>에 있는 정적 메서드를 대신 사용할 수 있습니다.  그러한 메서드 중 하나를 사용하여 디렉터리를 복제하는 방법의 예는 다음과 같습니다.  
  
 [!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces3.cs#20)]  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [네임스페이스](../../../csharp/programming-guide/namespaces/index.md)   
 [네임스페이스 사용](../../../csharp/programming-guide/namespaces/using-namespaces.md)