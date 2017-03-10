---
redirect_url: /dotnet/articles/csharp/linq/join-by-using-composite-keys
caps.handback.revision: 8
---
# 방법: 복합 키를 사용하여 조인(C# 프로그래밍 가이드)
이 예제에서는 둘 이상의 키를 사용하여 일치 항목을 정의하기 위해 조인 연산을 수행하는 방법을 보여 줍니다.  조인 연산을 수행하려면 복합 키를 사용합니다.  익명 형식의 복합 키를 만들거나, 비교할 값이 포함된 명명된 형식으로 복합 키를 만듭니다.  메서드 경계를 넘어서 쿼리 변수를 전달하려면 키의 <xref:System.Object.Equals%2A> 및 <xref:System.Object.GetHashCode%2A>를 재정의하는 명명된 형식을 사용합니다.  각 키는 속성 이름 및 속성 순서가 동일해야 합니다.  
  
## 예제  
 다음 예제에서는 복합 키를 사용하여 세 테이블의 데이터를 조인하는 방법을 보여 줍니다.  
  
```  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,         d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 복합 키의 형식 유추는 키의 속성 이름과 속성 순서에 따라 달라집니다.  소스 시퀀스에서 속성의 이름이 같지 않으면 키에 새 이름을 지정해야 합니다.  예를 들어 `Orders` 테이블과 `OrderDetails` 테이블의 열 이름이 서로 다르면 다음과 같이 익명 형식의 동일한 이름을 지정하여 복합 키를 만들 수 있습니다.  
  
```  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 복합 키는 `group` 절에서도 사용할 수 있습니다.  
  
## 코드 컴파일  
  
-   이 코드를 컴파일하고 실행하려면 다음 단계를 수행하십시오.  
  
-   [방법: Northwind 데이터베이스에 연결](../Topic/How%20to:%20Connect%20to%20the%20Northwind%20Database.md)를 연 다음 지침에 따라 프로젝트를 설정하고 데이터베이스 연결을 만듭니다.  자세한 내용은 [방법: 샘플 데이터베이스 설치](../Topic/How%20to:%20Install%20Sample%20Databases.md)를 참조하십시오.  
  
-   samples.cs에서 이 파일의 다른 메서드와 비슷하게 db라는 이름의 Northwind 입력 매개 변수를 사용하는 빈 메서드를 새로 만듭니다.  그런 다음 이 예제의 코드를 메서드 본문에 붙여 넣습니다.  
  
-   `Main`에서 새 메서드를 호출하도록 program.cs를 수정합니다.  
  
-   F5 키를 눌러 쿼리를 컴파일하고 실행합니다.  
  
## 참고 항목  
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [join 절](../../../csharp/language-reference/keywords/join-clause.md)   
 [group 절](../../../csharp/language-reference/keywords/group-clause.md)