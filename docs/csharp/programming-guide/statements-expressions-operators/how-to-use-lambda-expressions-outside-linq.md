---
title: "방법: LINQ 외부에 람다 식 사용(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "람다 식[C#], 외부 LINQ"
ms.assetid: 2b519274-6ee4-4455-ab2e-aed67dbfd07c
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: LINQ 외부에 람다 식 사용(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

람다 식은 [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq_md.md)] 쿼리에만 제한되지 않습니다.  대리자 값을 사용할 수 있는 위치, 즉 무명 메서드를 사용할 수 있는 모든 위치에서 람다 식을 사용할 수 있습니다.  다음 예제에서는 Windows Forms 이벤트 처리기에서 람다 식을 사용하는 방법을 보여 줍니다.  이 예제에서 입력 값\(<xref:System.Object> 및 <xref:System.Windows.Forms.MouseEventArgs>\)의 형식은 컴파일러에서 유추되기 때문에 람다 입력 매개 변수에 명시적으로 지정할 필요가 없습니다.  
  
## 예제  
  
```  
public partial class Form1 : Form  
{  
    public Form1()  
    {  
        InitializeComponent();  
        // Use a lambda expression to define an event handler.  
       this.Click += (s, e) => { MessageBox.Show(((MouseEventArgs)e).Location.ToString());};  
    }  
}  
```  
  
## 참고 항목  
 [람다 식](../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md)   
 [무명 메서드](../../../csharp/programming-guide/statements-expressions-operators/anonymous-methods.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)