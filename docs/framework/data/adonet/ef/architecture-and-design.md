---
title: "아키텍처 및 디자인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd738d39-00e2-4bab-b387-90aac1a014bd
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: ce16e89e697a7865a65d86b408e49b5ad671bae1
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2018
---
# <a name="architecture-and-design"></a><span data-ttu-id="b7fa4-102">아키텍처 및 디자인</span><span class="sxs-lookup"><span data-stu-id="b7fa4-102">Architecture and Design</span></span>
<span data-ttu-id="b7fa4-103">SQL 생성 모듈은 [샘플 공급자](http://go.microsoft.com/fwlink/?LinkId=180616) 명령 트리를 나타내는 식 트리 방문자로 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-103">The SQL generation module in the [Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) is implemented as a visitor on the expression tree that represents the command tree.</span></span> <span data-ttu-id="b7fa4-104">생성은 식 트리에 대한 단일 패스로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-104">The generation is done in a single pass over the expression tree.</span></span>  
  
 <span data-ttu-id="b7fa4-105">트리의 노드는 아래쪽에서 위쪽으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-105">The nodes of the tree are processed from the bottom up.</span></span> <span data-ttu-id="b7fa4-106">먼저 중간 구조인 SqlSelectStatement 또는 SqlBuilder가 생성되며, 둘 다 ISqlFragment를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-106">First, an intermediate structure is produced: SqlSelectStatement or SqlBuilder, both implementing ISqlFragment.</span></span> <span data-ttu-id="b7fa4-107">그런 다음 이 구조에서 SQL 문 문자열이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-107">Next, the string SQL statement is produced from that structure.</span></span> <span data-ttu-id="b7fa4-108">중간 구조를 사용하는 이유는 두 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-108">There are two reasons for the intermediate structure:</span></span>  
  
-   <span data-ttu-id="b7fa4-109">논리적으로 SQL SELECT 문은 순서에 관계없이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-109">Logically, a SQL SELECT statement is populated out of order.</span></span> <span data-ttu-id="b7fa4-110">FROM 절에 참여하는 노드는 WHERE, GROUP BY 및 ORDER BY 절에 참여하는 노드 전에 방문됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-110">The nodes that participate in the FROM clause are visited before the nodes that participate in the WHERE, GROUP BY, and the ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="b7fa4-111">별칭의 이름을 바꾸려면 이름을 바꾸는 동안 충돌을 방지하기 위해 사용되는 모든 별칭을 식별해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-111">To rename aliases, you must identify all used aliases to avoid collisions during renaming.</span></span> <span data-ttu-id="b7fa4-112">SqlBuilder에서 이름 바꾸기 선택을 지연하려면 Symbol 개체를 사용하여 이름을 바꿀 후보인 열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-112">To defer the renaming choices in SqlBuilder, use Symbol objects to represent the columns that are candidates for renaming.</span></span>  
  
 <span data-ttu-id="b7fa4-113">![Diagram](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span><span class="sxs-lookup"><span data-stu-id="b7fa4-113">![Diagram](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span></span>  
  
 <span data-ttu-id="b7fa4-114">첫 번째 단계에서는 식 트리를 방문하는 동안 식이 SqlSelectStatement로 그룹화되고 조인이 평면화되며 조인 별칭이 평면화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-114">In the first phase, while visiting the expression tree, expressions are grouped into SqlSelectStatements, joins are flattened, and join aliases are flattened.</span></span> <span data-ttu-id="b7fa4-115">이 단계 중에 Symbol 개체는 이름을 바꿀 수 있는 열 또는 입력 별칭을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-115">During this pass, Symbol objects represent columns or input aliases that may be renamed.</span></span>  
  
 <span data-ttu-id="b7fa4-116">두 번째 단계에서는 실제 문자열을 생성하는 동안 별칭의 이름이 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-116">In the second phase, while producing the actual string, aliases are renamed.</span></span>  
  
## <a name="data-structures"></a><span data-ttu-id="b7fa4-117">데이터 구조</span><span class="sxs-lookup"><span data-stu-id="b7fa4-117">Data Structures</span></span>  
 <span data-ttu-id="b7fa4-118">이 섹션에 사용 되는 형식에 설명 된 [샘플 공급자](http://go.microsoft.com/fwlink/?LinkId=180616) SQL 문을 작성 하는 데 사용 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-118">This section discusses the types used in the [Sample Provider](http://go.microsoft.com/fwlink/?LinkId=180616) that you use to build a SQL statement.</span></span>  
  
### <a name="isqlfragment"></a><span data-ttu-id="b7fa4-119">ISqlFragment</span><span class="sxs-lookup"><span data-stu-id="b7fa4-119">ISqlFragment</span></span>  
 <span data-ttu-id="b7fa4-120">이 단원에서는 다음 두 가지 용도로 사용되는 ISqlFragment 인터페이스를 구현하는 클래스를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-120">This section covers the classes that implement the ISqlFragment interface, which serves two purposes:</span></span>  
  
-   <span data-ttu-id="b7fa4-121">모든 방문자 메서드에 대한 일반 반환 형식</span><span class="sxs-lookup"><span data-stu-id="b7fa4-121">A common return type for all the visitor methods.</span></span>  
  
-   <span data-ttu-id="b7fa4-122">최종 SQL 문자열을 작성하는 메서드 제공</span><span class="sxs-lookup"><span data-stu-id="b7fa4-122">Gives a method to write the final SQL string.</span></span>  
  
```  
internal interface ISqlFragment {  
   void WriteSql(SqlWriter writer, SqlGenerator sqlGenerator);  
}  
```  
  
#### <a name="sqlbuilder"></a><span data-ttu-id="b7fa4-123">SqlBuilder</span><span class="sxs-lookup"><span data-stu-id="b7fa4-123">SqlBuilder</span></span>  
 <span data-ttu-id="b7fa4-124">SqlBuilder는 StringBuilder와 마찬가지로 최종 SQL 문자열의 수집 장치입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-124">SqlBuilder is a gathering device for the final SQL string, similar to StringBuilder.</span></span> <span data-ttu-id="b7fa4-125">SqlBuilder는 문자열로 변환될 수 있는 ISqlFragment와 함께 최종 SQL을 구성하는 문자열로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-125">It consists of the strings that make up the final SQL, along with ISqlFragments that can be converted into strings.</span></span>  
  
```  
internal sealed class SqlBuilder : ISqlFragment {  
   public void Append(object s)  
   public void AppendLine()  
   public bool IsEmpty  
}  
```  
  
#### <a name="sqlselectstatement"></a><span data-ttu-id="b7fa4-126">SqlSelectStatement</span><span class="sxs-lookup"><span data-stu-id="b7fa4-126">SqlSelectStatement</span></span>  
 <span data-ttu-id="b7fa4-127">Sqlselectstatement는 "SELECT... 모양의 정식 SQL SELECT 문</span><span class="sxs-lookup"><span data-stu-id="b7fa4-127">SqlSelectStatement represents a canonical SQL SELECT statement of the shape "SELECT …</span></span> <span data-ttu-id="b7fa4-128">FROM  ..</span><span class="sxs-lookup"><span data-stu-id="b7fa4-128">FROM  ..</span></span> <span data-ttu-id="b7fa4-129">WHERE...</span><span class="sxs-lookup"><span data-stu-id="b7fa4-129">WHERE …</span></span> <span data-ttu-id="b7fa4-130">기준으로 그룹화 하는 중...</span><span class="sxs-lookup"><span data-stu-id="b7fa4-130">GROUP BY …</span></span> <span data-ttu-id="b7fa4-131">ORDER BY "입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-131">ORDER BY".</span></span>  
  
 <span data-ttu-id="b7fa4-132">각 SQL 절은 StringBuilder에 의해 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-132">Each of the SQL clauses is represented by a StringBuilder.</span></span> <span data-ttu-id="b7fa4-133">또한 Distinct가 지정되었는지 여부와 문이 맨 위에 있는지 여부를 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-133">In addition, it tracks whether Distinct has been specified and whether the statement is topmost.</span></span> <span data-ttu-id="b7fa4-134">문이 맨 위에 없는 경우 문에 TOP 절이 없으면 ORDER BY 절이 생략됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-134">If the statement is not topmost, the ORDER BY clause is omitted unless the statement also has a TOP clause.</span></span>  
  
 <span data-ttu-id="b7fa4-135">FromExtents에는 SELECT 문의 입력 목록이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-135">FromExtents contains the list of inputs for the SELECT statement.</span></span> <span data-ttu-id="b7fa4-136">여기에는 요소가 대개 하나만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-136">There is usually just one element in this.</span></span> <span data-ttu-id="b7fa4-137">조인의 SELECT 문에는 일시적으로 요소가 두 개 이상 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-137">SELECT statements for joins may temporarily have more than one element.</span></span>  
  
 <span data-ttu-id="b7fa4-138">SELECT 문이 Join 노드에 의해 만들어지면 SqlSelectStatement는 해당 조인에서 평면화된 모든 익스텐트의 목록을 AllJoinExtents에서 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-138">If the SELECT statement is created by a Join node, SqlSelectStatement maintains a list of all the extents that have been flattened in the join in AllJoinExtents.</span></span> <span data-ttu-id="b7fa4-139">OuterExtents는 SqlSelectStatement의 외부 참조를 나타내며 입력 별칭의 이름을 바꾸는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-139">OuterExtents represents outer references of the SqlSelectStatement and is used for input alias renaming.</span></span>  
  
```  
internal sealed class SqlSelectStatement : ISqlFragment {  
   internal bool IsDistinct { get, set };  
   internal bool IsTopMost  
  
   internal List<Symbol> AllJoinExtents { get, set };  
   internal List<Symbol> FromExtents { get};  
   internal Dictionary<Symbol, bool> OuterExtents { get};  
  
   internal TopClause Top { get, set };  
  
   internal SqlBuilder Select {get};  
   internal SqlBuilder From  
   internal SqlBuilder Where  
   internal SqlBuilder GroupBy  
   public SqlBuilder OrderBy  
}  
```  
  
#### <a name="topclause"></a><span data-ttu-id="b7fa4-140">TopClause</span><span class="sxs-lookup"><span data-stu-id="b7fa4-140">TopClause</span></span>  
 <span data-ttu-id="b7fa4-141">TopClause는 SqlSelectStatement에서 TOP 식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-141">TopClause represents the TOP expression in a SqlSelectStatement.</span></span> <span data-ttu-id="b7fa4-142">TopCount 속성은 선택할 TOP 행의 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-142">The TopCount property indicates how many TOP rows should be selected.</span></span>  <span data-ttu-id="b7fa4-143">WithTies가 true이면 TopClause는 DbLimitExpession에서 작성된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-143">When WithTies is true, the TopClause was built from a DbLimitExpession.</span></span>  
  
```  
class TopClause : ISqlFragment {  
   internal bool WithTies {get}  
   internal ISqlFragment TopCount {get}  
   internal TopClause(ISqlFragment topCount, bool withTies)  
   internal TopClause(int topCount, bool withTies)  
}  
```  
  
### <a name="symbols"></a><span data-ttu-id="b7fa4-144">기호</span><span class="sxs-lookup"><span data-stu-id="b7fa4-144">Symbols</span></span>  
 <span data-ttu-id="b7fa4-145">기호 관련 클래스와 기호 테이블은 입력 별칭 이름 바꾸기, 조인 별칭 평면화 및 열 별칭 이름 바꾸기를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-145">The Symbol-related classes and the symbol table perform input alias renaming, join alias flattening, and column alias renaming.</span></span>  
  
 <span data-ttu-id="b7fa4-146">Symbol 클래스는 익스텐트, 중첩된 SELECT 문 또는 열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-146">The Symbol class represents an extent, a nested SELECT statement, or a column.</span></span> <span data-ttu-id="b7fa4-147">이 클래스는 사용된 후 이름 바꾸기를 허용하기 위해 실제 별칭 대신 사용되며 나타내는 아티팩트(형식 등)에 대한 추가 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-147">It is used instead of an actual alias to allow for renaming after it has been used and it also carries additional information for the artifact it represents (like the type).</span></span>  
  
```  
class Symbol : ISqlFragment {  
   internal Dictionary<string, Symbol> Columns {get}  
   internal bool NeedsRenaming {get, set}  
   internal bool IsUnnest {get, set}   //not used  
  
   public string Name{get}  
   public string NewName {get,set}  
   internal TypeUsage Type {get, set}  
  
   public Symbol(string name, TypeUsage type)  
}  
```  
  
 <span data-ttu-id="b7fa4-148">Name은 표현된 익스텐트, 중첩된 SELECT 문 또는 열의 원래 별칭을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-148">Name stores the original alias for the represented extent, nested SELECT statement, or a column.</span></span>  
  
 <span data-ttu-id="b7fa4-149">NewName은 SQL SELECT 문에서 사용될 별칭을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-149">NewName stores the alias that will be used in the SQL SELECT statement.</span></span> <span data-ttu-id="b7fa4-150">NewName은 처음에는 Name으로 설정되며 최종 문자열 쿼리를 생성할 때 필요한 경우에만 이름이 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-150">It is originally set to Name, and only renamed if needed when generating the final string query.</span></span>  
  
 <span data-ttu-id="b7fa4-151">Type은 익스텐트와 중첩된 SELECT 문을 나타내는 기호에만 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-151">Type is only useful for symbols representing extents and nested SELECT statements.</span></span>  
  
#### <a name="symbolpair"></a><span data-ttu-id="b7fa4-152">SymbolPair</span><span class="sxs-lookup"><span data-stu-id="b7fa4-152">SymbolPair</span></span>  
 <span data-ttu-id="b7fa4-153">SymbolPair 클래스는 레코드 평면화를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-153">The SymbolPair class addresses record flattening.</span></span>  
  
 <span data-ttu-id="b7fa4-154">속성 식 D(v, "j3.j2.j1.a.x")를 살펴보겠습니다. 이 식에서 v는 VarRef이고 j1, j2, j3은 조인이며, a는 익스텐트이고 x는 열입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-154">Consider a property expression D(v, "j3.j2.j1.a.x") where v is a VarRef, j1, j2, j3 are joins, a is an extent, and x is a columns.</span></span>  
  
 <span data-ttu-id="b7fa4-155">이 식은 결국 {j'}.{x'}로 변환되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-155">This has to be translated eventually into {j'}.{x'}.</span></span> <span data-ttu-id="b7fa4-156">원본 필드는 조인 식(예: j2)을 나타내는 가장 바깥쪽의 SqlStatement를 나타내며, 항상 조인 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-156">The source field represents the outermost SqlStatement, representing a join expression (say j2); this is always a Join symbol.</span></span> <span data-ttu-id="b7fa4-157">열 필드는 한 조인 기호에서 다음 조인 기호로 이동하다가 조인 기호가 아닌 기호에서 멈춥니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-157">The column field moves from one join symbol to the next until it stops at a non-join symbol.</span></span> <span data-ttu-id="b7fa4-158">열 필드는 DbPropertyExpression을 방문할 때 반환되지만 SqlBuilder에 추가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-158">This is returned when visiting a DbPropertyExpression but is never added to a SqlBuilder.</span></span>  
  
```  
class SymbolPair : ISqlFragment {  
   public Symbol Source;  
   public Symbol Column;  
   public SymbolPair(Symbol source, Symbol column)  
}  
```  
  
#### <a name="joinsymbol"></a><span data-ttu-id="b7fa4-159">JoinSymbol</span><span class="sxs-lookup"><span data-stu-id="b7fa4-159">JoinSymbol</span></span>  
 <span data-ttu-id="b7fa4-160">조인 기호는 조인 또는 조인 입력과 함께 중첩된 SELECT 문을 나타내는 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-160">A Join symbol is a Symbol that represents a nested SELECT statement with a join or a join input.</span></span>  
  
```  
internal sealed class JoinSymbol : Symbol {  
   internal List<Symbol> ColumnList {get, set}  
   internal List<Symbol> ExtentList {get}  
   internal List<Symbol> FlattenedExtentList {get, set}  
   internal Dictionary<string, Symbol> NameToExtent {get}  
   internal bool IsNestedJoin {get, set}  
  
   public JoinSymbol(string name, TypeUsage type, List<Symbol> extents)  
}  
```  
  
 <span data-ttu-id="b7fa4-161">ColumnList는 이 기호가 SQL SELECT 문을 나타내는 경우 SELECT 절의 열 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-161">ColumnList represents the list of columns in the SELECT clause if this symbol represents a SQL SELECT statement.</span></span> <span data-ttu-id="b7fa4-162">ExtentList는 SELECT 절의 익스텐트 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-162">ExtentList is the list of extents in the SELECT clause.</span></span> <span data-ttu-id="b7fa4-163">조인에 최상위 수준에서 평면화된 여러 익스텐트가 있는 경우 FlattenedExtentList는 익스텐트를 추적하여 익스텐트 별칭의 이름이 올바르게 바뀌도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-163">If the join has multiple extents flattened at the top level, FlattenedExtentList tracks the extents to ensure that extent aliases are renamed correctly.</span></span>  
  
 <span data-ttu-id="b7fa4-164">NameToExtent의 경우 사전인 ExtentList에 모든 익스텐트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-164">NameToExtent has all the extents in ExtentList as a dictionary.</span></span> <span data-ttu-id="b7fa4-165">IsNestedJoin은 JoinSymbol이 일반 조인 기호인지 아니면 해당 SqlSelectStatement가 있는 기호인지를 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-165">IsNestedJoin is used to determine whether a JoinSymbol is an ordinary join symbol or one that has a corresponding SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="b7fa4-166">모든 목록은 한 번만 설정된 다음 조회나 열거에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-166">All the lists are set exactly once and then used for lookups or enumeration.</span></span>  
  
#### <a name="symboltable"></a><span data-ttu-id="b7fa4-167">SymbolTable</span><span class="sxs-lookup"><span data-stu-id="b7fa4-167">SymbolTable</span></span>  
 <span data-ttu-id="b7fa4-168">SymbolTable은 변수 이름을 기호로 확인하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-168">SymbolTable is used to resolve variable names to Symbols.</span></span> <span data-ttu-id="b7fa4-169">SymbolTable은 각 범위에 대한 새 항목이 있는 스택으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-169">SymbolTable is implemented as a stack with a new entry for each scope.</span></span> <span data-ttu-id="b7fa4-170">Lookup은 항목이 발견될 때까지 스택의 위쪽에서 아래쪽까지 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-170">Lookups search from the top of the stack to the bottom until an entry is found.</span></span>  
  
```  
internal sealed class SymbolTable {  
   internal void EnterScope()  
   internal void ExitScope()  
   internal void Add(string name, Symbol value)  
   internal Symbol Lookup(string name)  
}  
```  
  
 <span data-ttu-id="b7fa4-171">SQL 생성 모듈의 인스턴스마다 SymbolTable이 하나만 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-171">There is only one SymbolTable per one instance of the Sql Generation module.</span></span> <span data-ttu-id="b7fa4-172">각 관계형 노드의 범위에 들어갔다가 나오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-172">Scopes are entered and exited for each relational node.</span></span> <span data-ttu-id="b7fa4-173">이전 범위에 있는 모든 기호는 동일한 이름의 다른 기호에 의해 숨겨지지 않는 한 이후 범위에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-173">All symbols in earlier scopes are visible to later scopes unless hidden by other symbols with the same name.</span></span>  
  
### <a name="global-state-for-the-visitor"></a><span data-ttu-id="b7fa4-174">방문자의 전역 상태</span><span class="sxs-lookup"><span data-stu-id="b7fa4-174">Global State for the Visitor</span></span>  
 <span data-ttu-id="b7fa4-175">별칭과 열의 이름을 쉽게 바꾸도록 하기 위해 쿼리 트리에 대한 첫 번째 패스에서 사용된 모든 열 이름(AllColumnNames) 및 익스텐트 별칭(AllExtentNames)의 목록을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-175">To assist in renaming of aliases and columns, maintain a list of all the column names (AllColumnNames) and extent aliases (AllExtentNames) that have been used in the first pass over the query tree.</span></span>  <span data-ttu-id="b7fa4-176">기호 테이블은 변수 이름을 기호로 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-176">The symbol table resolves variable names to Symbols.</span></span> <span data-ttu-id="b7fa4-177">IsVarRefSingle은 확인 용도에만 사용되며 반드시 필요하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-177">IsVarRefSingle is only used for verification purposes, it is not strictly necessary.</span></span>  
  
 <span data-ttu-id="b7fa4-178">사용되는 두 스택 CurrentSelectStatement 및 IsParentAJoin은 방문자 패턴이 매개 변수를 전달할 수 있도록 허용하지 않으므로 부모에서 자식 노드로 "매개 변수"를 전달하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-178">The two stacks used via CurrentSelectStatement and IsParentAJoin are used to pass "parameters" from parent to child nodes, since the visitor pattern does not allow us to pass parameters.</span></span>  
  
```  
internal Dictionary<string, int> AllExtentNames {get}  
internal Dictionary<string, int> AllColumnNames {get}  
SymbolTable symbolTable = new SymbolTable();  
bool isVarRefSingle = false;  
  
Stack<SqlSelectStatement> selectStatementStack;  
private SqlSelectStatement CurrentSelectStatement{get}  
  
Stack<bool> isParentAJoinStack;  
private bool IsParentAJoin{get}  
```  
  
## <a name="common-scenarios"></a><span data-ttu-id="b7fa4-179">일반적인 시나리오</span><span class="sxs-lookup"><span data-stu-id="b7fa4-179">Common Scenarios</span></span>  
 <span data-ttu-id="b7fa4-180">이 단원에서는 일반 공급자 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-180">This section discusses common provider scenarios.</span></span>  
  
### <a name="grouping-expression-nodes-into-sql-statements"></a><span data-ttu-id="b7fa4-181">SQL 문으로 식 노드 그룹화</span><span class="sxs-lookup"><span data-stu-id="b7fa4-181">Grouping Expression Nodes into SQL Statements</span></span>  
 <span data-ttu-id="b7fa4-182">SqlSelectStatement는 트리를 아래쪽에서 위쪽으로 방문할 때 첫 번째 관계형 노드(일반적으로 DbScanExpression 익스텐트)를 발견하면 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-182">A SqlSelectStatement is created when the first relational node is encountered (typically a DbScanExpression extent) when visiting the tree from the bottom up.</span></span> <span data-ttu-id="b7fa4-183">중첩 쿼리가 가능한 한 적은 SQL SELECT 문을 생성하려면 해당 SqlSelectStatement에서 가능한 한 많은 부모 노드를 집계합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-183">To produce a SQL SELECT statement with as few nested queries as possible, aggregate as many of its parent nodes as possible in that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="b7fa4-184">지정된(관계형) 노드를 현재 SqlSelectStatement(입력을 방문할 때 반환되는 항목)에 추가할 수 있는지 여부나 새 문을 시작해야 하는지 여부는 IsCompatible 메서드에서 계산되며 지정된 노드 아래에 있던 노드에 따라 SqlSelectStatement에 이미 있는 항목에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-184">The decision of whether a given (relational) node can be added to the current SqlSelectStatement (the one returned when visiting the input) or if a new statement needs to be started is computed by the method IsCompatible and depends on what is already in the SqlSelectStatement, which depends on what nodes were below the given node.</span></span>  
  
 <span data-ttu-id="b7fa4-185">일반적으로 병합이 고려되는 노드가 비어 있지 않은 절 뒤에서 SQL 문 절이 계산되는 경우 해당 노드를 현재 문에 추가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-185">Typically, if SQL statement clauses are evaluated after clauses where the nodes being considered for merging are not empty, the node cannot be added to the current statement.</span></span> <span data-ttu-id="b7fa4-186">예를 들어, 다음 노드가 Filter인 경우 다음 조건에 해당하는 경우에만 이 노드를 현재 SqlSelectStatement에 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-186">For example, if the next node is a Filter, that node can be incorporated into the current SqlSelectStatement only if the following is true:</span></span>  
  
-   <span data-ttu-id="b7fa4-187">SELECT 목록이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-187">The SELECT list is empty.</span></span> <span data-ttu-id="b7fa4-188">SELECT 목록이 비어 있지 않으면 필터 앞의 노드에 의해 생성되며 조건자는 해당 SELECT 목록을 통해 생성된 열을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-188">If the SELECT list is not empty, the select list was produced by a node preceding the filter and the predicate may refer to columns produced by that SELECT list.</span></span>  
  
-   <span data-ttu-id="b7fa4-189">GROUPBY가 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-189">The GROUPBY is empty.</span></span> <span data-ttu-id="b7fa4-190">GROUPBY가 비어 있지 않은 경우 필터를 추가하면 그룹화 전의 필터링을 의미하므로 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-190">If the GROUPBY is not empty, adding the filter would mean filtering before grouping, which is not correct.</span></span>  
  
-   <span data-ttu-id="b7fa4-191">TOP 절이 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-191">The TOP clause is empty.</span></span> <span data-ttu-id="b7fa4-192">TOP 절이 비어 있지 않은 경우 필터를 추가하면 TOP을 수행하기 전의 필터링을 의미하므로 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-192">If the TOP clause is not empty, adding the filter would mean filtering before doing TOP, which is not correct.</span></span>  
  
 <span data-ttu-id="b7fa4-193">이는 산술 식 또는 DbConstantExpression과 같은 관계형 노드가 아닌 노드에는 적용되지 않습니다. 이러한 노드는 항상 기존 SqlSelectStatement의 일부로 포함되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-193">This does not apply to non-relational nodes like DbConstantExpression or arithmetic expressions, because these are always included as part of an existing SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="b7fa4-194">또한 조인 트리의 루트(조인 부모가 없는 조인 노드)를 발견할 때 새 SqlSelectStatement가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-194">Also, when encountering the root of join tree (a join node that does not have a join parent), a new SqlSelectStatement is started.</span></span> <span data-ttu-id="b7fa4-195">왼쪽 편에 있는 모든 조인 자식은 이 SqlSelectStatement에 집계됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-195">All of its left spine join children are aggregated into that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="b7fa4-196">새 SqlSelectStatement가 시작되고 현재 SqlSelectStatement가 입력에 추가될 때마다 프로젝션 열(SELECT 절)이 없는 경우 프로젝션 열을 추가하여 현재 SqlSelectStatement를 완성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-196">Whenever a new SqlSelectStatement is started, and the current one is added to the input, the current SqlSelectStatement may need to be completed by adding projection columns (a SELECT clause) if one does not exist.</span></span> <span data-ttu-id="b7fa4-197">이 작업은 AddDefaultColumns 메서드를 사용하여 수행됩니다. 이 메서드는 SqlSelectStatement의 FromExtents를 확인하고 FromExtents가 나타내는 익스텐트의 목록이 범위에서 제공하는 모든 열을 프로젝션된 열의 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-197">This is done with the method AddDefaultColumns, which looks at the FromExtents of the SqlSelectStatement and adds all the columns that the list of extents represented by FromExtents brings in scope to the list of projected columns.</span></span> <span data-ttu-id="b7fa4-198">이 작업은 이 시점에서 다른 노드가 참조하는 열을 알 수 없기 때문에 수행되며</span><span class="sxs-lookup"><span data-stu-id="b7fa4-198">This is done, because at that point, it is unknown which columns are referenced by the other nodes.</span></span> <span data-ttu-id="b7fa4-199">나중에 사용될 수 있는 열만 프로젝션하도록 최적화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-199">This can be optimized to only project the columns that can later be used.</span></span>  
  
### <a name="join-flattening"></a><span data-ttu-id="b7fa4-200">조인 평면화</span><span class="sxs-lookup"><span data-stu-id="b7fa4-200">Join Flattening</span></span>  
 <span data-ttu-id="b7fa4-201">IsParentAJoin 속성은 지정된 조인을 평면화할 수 있는지 여부를 확인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-201">The IsParentAJoin property helps determine whether a given join can be flattened.</span></span> <span data-ttu-id="b7fa4-202">특히 IsParentAJoin은 조인의 왼쪽 자식과 조인의 직접 입력인 각 DbScanExpression에 대해서만 `true`를 반환합니다. 이 경우 자식 노드는 부모가 나중에 사용할 동일한 SqlSelectStatement를 다시 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-202">In particular, IsParentAJoin returns `true` only for the left child of a join and for each DbScanExpression that is an immediate input to a join, in which case that child node reuses the same SqlSelectStatement that the parent would later use.</span></span> <span data-ttu-id="b7fa4-203">자세한 내용은 "조인 식"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-203">For more information, see "Join Expressions".</span></span>  
  
### <a name="input-alias-redirecting"></a><span data-ttu-id="b7fa4-204">입력 별칭 리디렉션</span><span class="sxs-lookup"><span data-stu-id="b7fa4-204">Input Alias Redirecting</span></span>  
 <span data-ttu-id="b7fa4-205">입력 별칭 리디렉션은 기호 테이블을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-205">Input alias redirecting is accomplished with the symbol table.</span></span>  
  
 <span data-ttu-id="b7fa4-206">첫 번째 예제를 참조 입력된 별칭 리디렉션을 설명, [명령 트리-모범 사례에서에서 sql 문을 생성](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-206">To explain input alias redirecting, refer to the first example in [Generating SQL from Command Trees - Best Practices](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md).</span></span>  <span data-ttu-id="b7fa4-207">이 예제에서 "a"는 프로젝션에서 "b"로 리디렉션되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-207">There "a" needed to be redirected to "b" in the projection.</span></span>  
  
 <span data-ttu-id="b7fa4-208">SqlSelectStatement 개체가 만들어지면 노드의 입력인 익스텐트가 SqlSelectStatement의 From 속성에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-208">When a SqlSelectStatement object is created, the extent that is the input to the node is put in the From property of the SqlSelectStatement.</span></span> <span data-ttu-id="b7fa4-209">기호(<symbol_b>)가 이 익스텐트를 나타내기 위해 입력 바인딩 이름("b")을 기반으로 만들어지며 "AS  " + <symbol_b>가 FROM 절에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-209">A Symbol (<symbol_b>) is created based on the input binding name ("b") to represent that extent and "AS  " +  <symbol_b> is appended to the From Clause.</span></span>  <span data-ttu-id="b7fa4-210">이 기호는 FromExtents 속성에도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-210">The symbol is also added to the FromExtents property.</span></span>  
  
 <span data-ttu-id="b7fa4-211">이 기호는 입력 바인딩 이름을 해당 기호에 연결하기 위해 기호 테이블에도 추가됩니다("b", <symbol_b>).</span><span class="sxs-lookup"><span data-stu-id="b7fa4-211">The symbol is also added to the symbol table to link the input binding name to it ("b", <symbol_b>).</span></span>  
  
 <span data-ttu-id="b7fa4-212">이후의 노드는 이 SqlSelectStatement를 다시 사용하는 경우 입력 바인딩 이름을 해당 기호에 연결하기 위해 기호 테이블에 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-212">If a subsequent node reuses that SqlSelectStatement, it adds an entry to the symbol table to link its input binding name to that symbol.</span></span> <span data-ttu-id="b7fa4-213">예제에서는 입력된 바인딩 이름이 "a" 인 DbProjectExpression은 SqlSelectStatement를 다시 사용 하 고 추가 ("a", \< symbol_b >) 테이블에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-213">In our example, the DbProjectExpression with the input binding name of "a" would reuse the SqlSelectStatement and add ("a", \< symbol_b>) to the table.</span></span>  
  
 <span data-ttu-id="b7fa4-214">식에서 SqlSelectStatement를 다시 사용하는 노드의 입력 바인딩 이름을 참조하는 경우 이 참조는 기호 테이블을 사용하여 올바른 리디렉션된 기호로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-214">When expressions reference the input binding name of the node that is reusing the SqlSelectStatement, that reference is resolved using the symbol table to the correct redirected symbol.</span></span> <span data-ttu-id="b7fa4-215">"a"를 나타내는 DbVariableReferenceExpression을 방문하는 동안 "a.x"의 "a"가 확인될 때 기호 <symbol_b>로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-215">When "a" from "a.x" is resolved while visiting the DbVariableReferenceExpression representing "a" it will resolve to the Symbol <symbol_b>.</span></span>  
  
### <a name="join-alias-flattening"></a><span data-ttu-id="b7fa4-216">조인 별칭 평면화</span><span class="sxs-lookup"><span data-stu-id="b7fa4-216">Join Alias Flattening</span></span>  
 <span data-ttu-id="b7fa4-217">조인 별칭 평면화는 DbPropertyExpression 단원에 설명된 대로 DbPropertyExpression을 방문할 때 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-217">Join alias flattening is achieved when visiting a DbPropertyExpression as described in the section titled DbPropertyExpression.</span></span>  
  
### <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="b7fa4-218">열 이름 및 익스텐트 별칭 이름 바꾸기</span><span class="sxs-lookup"><span data-stu-id="b7fa4-218">Column Name and Extent Alias Renaming</span></span>  
 <span data-ttu-id="b7fa4-219">열 이름 및 익스텐트 별칭 이름 바꾸기의 문제는 SQL 생성의 두 번째 단계: 문자열 명령 생성 단원에 설명된 대로 생성의 두 번째 단계에서 별칭으로만 대체되는 기호를 사용하여 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-219">The issue of column name and extent alias renaming is addressed by using symbols that only get substituted with aliases in the second phase of the generation described in the section titled Second Phase of SQL Generation: Generating the String Command.</span></span>  
  
## <a name="first-phase-of-the-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="b7fa4-220">SQL 생성의 첫 번째 단계: 식 트리 방문</span><span class="sxs-lookup"><span data-stu-id="b7fa4-220">First Phase of the SQL Generation: Visiting the Expression Tree</span></span>  
 <span data-ttu-id="b7fa4-221">이 단원에서는 쿼리를 나타내는 식이 방문되고 중간 구조 SqlSelectStatement 또는 SqlBuilder가 생성되는 SQL 생성의 첫 번째 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-221">This section describes the first phase of SQL generation, when the expression representing the query is visited and an intermediate structure is produced, either a SqlSelectStatement or a SqlBuilder.</span></span>  
  
 <span data-ttu-id="b7fa4-222">이 단원에서는 여러 식 노드 범주의 방문 원칙과 특정 식 형식 방문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-222">This section describes the principles of visiting different expression node categories, and details of visiting specific expression types.</span></span>  
  
### <a name="relational-non-join-nodes"></a><span data-ttu-id="b7fa4-223">관계형(비조인) 노드</span><span class="sxs-lookup"><span data-stu-id="b7fa4-223">Relational (Non-Join) Nodes</span></span>  
 <span data-ttu-id="b7fa4-224">다음 식 형식은 비조인 노드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-224">The following expression types support non-join nodes:</span></span>  
  
-   <span data-ttu-id="b7fa4-225">DbDistinctExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-225">DbDistinctExpression</span></span>  
  
-   <span data-ttu-id="b7fa4-226">DbFilterExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-226">DbFilterExpression</span></span>  
  
-   <span data-ttu-id="b7fa4-227">DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-227">DbGroupByExpression</span></span>  
  
-   <span data-ttu-id="b7fa4-228">DbLimitExpession</span><span class="sxs-lookup"><span data-stu-id="b7fa4-228">DbLimitExpession</span></span>  
  
-   <span data-ttu-id="b7fa4-229">DbProjectExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-229">DbProjectExpression</span></span>  
  
-   <span data-ttu-id="b7fa4-230">DbSkipExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-230">DbSkipExpression</span></span>  
  
-   <span data-ttu-id="b7fa4-231">DbSortExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-231">DbSortExpression</span></span>  
  
 <span data-ttu-id="b7fa4-232">이러한 노드 방문은 다음과 같은 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-232">Visiting these nodes follows the following pattern:</span></span>  
  
1.  <span data-ttu-id="b7fa4-233">관계형 입력을 방문하고 결과로 생성되는 SqlSelectStatement를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-233">Visit the relational input and get the resulting SqlSelectStatement.</span></span> <span data-ttu-id="b7fa4-234">관계형 노드의 입력은 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-234">The input to a relational node could be one of the following:</span></span>  
  
    -   <span data-ttu-id="b7fa4-235">익스텐트(예: DbScanExpression)를 포함하는 관계형 노드.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-235">A relational node, including an extent (a DbScanExpression, for example).</span></span> <span data-ttu-id="b7fa4-236">이러한 노드를 방문하면 SqlSelectStatement가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-236">Visiting such a node returns a SqlSelectStatement.</span></span>  
  
    -   <span data-ttu-id="b7fa4-237">집합 연산 식(예: UNION ALL).</span><span class="sxs-lookup"><span data-stu-id="b7fa4-237">A set operation expression (UNION ALL, for example).</span></span> <span data-ttu-id="b7fa4-238">결과는 대괄호로 래핑되어야 하며 새 SqlSelectStatement의 FROM 절에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-238">The result has to be wrapped in brackets and put in the FROM clause of a new SqlSelectStatement.</span></span>  
  
2.  <span data-ttu-id="b7fa4-239">입력을 통해 생성되는 SqlSelectStatement에 현재 노드를 추가할 수 있는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-239">Check whether the current node can be added to the SqlSelectStatement produced by the input.</span></span> <span data-ttu-id="b7fa4-240">SQL 문으로 식 그룹화 단원에서 이에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-240">The section titled Grouping Expressions into SQL Statements describes this.</span></span> <span data-ttu-id="b7fa4-241">추가할 수 없는 경우에는 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-241">If not,</span></span>  
  
    -   <span data-ttu-id="b7fa4-242">현재 SqlSelectStatement 개체를 꺼냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-242">Pop the current SqlSelectStatement object.</span></span>  
  
    -   <span data-ttu-id="b7fa4-243">새 SqlSelectStatement 개체를 만들고 꺼낸 SqlSelectStatement를 새 SqlSelectStatement 개체의 FROM으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-243">Create a new SqlSelectStatement object and add the popped SqlSelectStatement as the FROM of the new SqlSelectStatement object.</span></span>  
  
    -   <span data-ttu-id="b7fa4-244">스택 맨 위에 새 개체를 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-244">Put the new object on top of the stack.</span></span>  
  
3.  <span data-ttu-id="b7fa4-245">입력에서 올바른 기호로 입력 식 바인딩을 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-245">Redirect the input expression binding to the correct symbol from the input.</span></span> <span data-ttu-id="b7fa4-246">이 정보는 SqlSelectStatement 개체에서 유지 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-246">This information is maintained in the SqlSelectStatement object.</span></span>  
  
4.  <span data-ttu-id="b7fa4-247">새 SymbolTable 범위를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-247">Add a new SymbolTable scope.</span></span>  
  
5.  <span data-ttu-id="b7fa4-248">식의 비입력 부분(예: Projection 및 Predicate)을 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-248">Visit the non-input part of the expression (for example, Projection and Predicate).</span></span>  
  
6.  <span data-ttu-id="b7fa4-249">전역 스택에 추가된 모든 개체를 꺼냅니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-249">Pop all the objects added to the global stacks.</span></span>  
  
 <span data-ttu-id="b7fa4-250">DbSkipExpression은 SQL에서 직접 해당하는 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-250">DbSkipExpression not have a direct equivalent in SQL.</span></span> <span data-ttu-id="b7fa4-251">논리적으로 DbSkipExpression은 다음으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-251">Logically, it is translated into:</span></span>  
  
```  
SELECT Y.x1, Y.x2, ..., Y.xn  
FROM (  
   SELECT X.x1, X.x2, ..., X.xn, row_number() OVER (ORDER BY sk1, sk2, ...) AS [row_number]   
   FROM input as X   
   ) as Y  
WHERE Y.[row_number] > count   
ORDER BY sk1, sk2, ...  
```  
  
### <a name="join-expressions"></a><span data-ttu-id="b7fa4-252">조인 식</span><span class="sxs-lookup"><span data-stu-id="b7fa4-252">Join Expressions</span></span>  
 <span data-ttu-id="b7fa4-253">다음은 조인 식으로 간주되며 VisitJoinExpression 메서드에 의해 공통적인 방식으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-253">The following are considered join expressions and they are processed in a common way, by the VisitJoinExpression method:</span></span>  
  
-   <span data-ttu-id="b7fa4-254">DbApplyExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-254">DbApplyExpression</span></span>  
  
-   <span data-ttu-id="b7fa4-255">DbJoinExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-255">DbJoinExpression</span></span>  
  
-   <span data-ttu-id="b7fa4-256">DbCrossJoinExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-256">DbCrossJoinExpression</span></span>  
  
 <span data-ttu-id="b7fa4-257">방문 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-257">The following are the visit steps:</span></span>  
  
 <span data-ttu-id="b7fa4-258">첫 번째 단계로, 자식을 방문하기 전에 IsParentAJoin이 호출되어 조인 노드가 왼쪽 편에 있는 조인의 자식인지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-258">First, before visiting the children, IsParentAJoin is invoked to check whether the join node is a child of a join along a left spine.</span></span> <span data-ttu-id="b7fa4-259">IsParentAJoin이 false를 반환하면 새 SqlSelectStatement가 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-259">If it returns false, a new SqlSelectStatement is started.</span></span> <span data-ttu-id="b7fa4-260">부모(조인 노드)가 자식이 이후에 사용할 수 있도록 SqlSelectStatement를 만들기 때문에 조인은 나머지 노드와 다르게 방문됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-260">In that sense, joins are visited differently from the rest of the nodes, as the parent (the join node) creates the SqlSelectStatement for the children to possibly use.</span></span>  
  
 <span data-ttu-id="b7fa4-261">두 번째 단계로, 입력을 한 번에 하나씩 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-261">Second, process the inputs one at a time.</span></span> <span data-ttu-id="b7fa4-262">각 입력에 대해 다음 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-262">For each input:</span></span>  
  
1.  <span data-ttu-id="b7fa4-263">입력을 방문합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-263">Visit the input.</span></span>  
  
2.  <span data-ttu-id="b7fa4-264">ProcessJoinInputResult를 호출하여 입력을 방문한 결과를 사후 처리합니다. ProcessJoinInputResult는 조인 식의 자식을 방문하고 자식에 의해 생성된 SqlSelectStatement를 완료한 후 기호 테이블을 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-264">Post process the result of visiting the input by invoking ProcessJoinInputResult, which is responsible for maintaining the symbol table after visiting a child of a join expression and possibly finishing the SqlSelectStatement produced by the child.</span></span> <span data-ttu-id="b7fa4-265">자식의 결과는 다음 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-265">The child's result could be one of the following:</span></span>  
  
    -   <span data-ttu-id="b7fa4-266">부모가 추가될 것과 다른 SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-266">A SqlSelectStatement different from the one to which the parent will be added.</span></span> <span data-ttu-id="b7fa4-267">이러한 경우에는 기본 열을 추가하여 SqlSelectStatement를 완성해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-267">In such case, it may need to be completed by adding default columns.</span></span> <span data-ttu-id="b7fa4-268">입력이 조인이면 새 조인 기호를 만들어야 하고,</span><span class="sxs-lookup"><span data-stu-id="b7fa4-268">If the input was a Join, you need to create a new join symbol.</span></span> <span data-ttu-id="b7fa4-269">그렇지 않으면 일반 기호를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-269">Otherwise, create a normal symbol.</span></span>  
  
    -   <span data-ttu-id="b7fa4-270">부모의 SqlSelectStatement에 대한 입력 목록에 추가되기만 하는 익스텐트(예: DbScanExpression)</span><span class="sxs-lookup"><span data-stu-id="b7fa4-270">An extent (a DbScanExpression, for example), in which case it is simply added to the list of inputs of the parent’s SqlSelectStatement.</span></span>  
  
    -   <span data-ttu-id="b7fa4-271">SqlSelectStatement 이외의 항목. 이 경우 대괄호로 래핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-271">Not a SqlSelectStatement, in which case it is wrapped with brackets.</span></span>  
  
    -   <span data-ttu-id="b7fa4-272">부모가 추가된 동일한 SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-272">The same SqlSelectStatement to which the parent is added.</span></span> <span data-ttu-id="b7fa4-273">이러한 경우 FromExtents 목록의 기호가 이러한 기호를 모두 나타내는 하나의 새 JoinSymbol로 대체되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-273">In such case, the symbols in the FromExtents list need to be replaced with a single new JoinSymbol representing them all.</span></span>  
  
    -   <span data-ttu-id="b7fa4-274">처음 세 경우에는 AddFromSymbol이 호출되어 AS 절을 추가하고 기호 테이블을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-274">For the first three cases, AddFromSymbol is called to add the AS clause, and update the symbol table.</span></span>  
  
 <span data-ttu-id="b7fa4-275">세 번째 단계로, 조인 조건(있는 경우)이 방문됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-275">Third, the join condition (if any) is visited.</span></span>  
  
### <a name="set-operations"></a><span data-ttu-id="b7fa4-276">집합 작업</span><span class="sxs-lookup"><span data-stu-id="b7fa4-276">Set Operations</span></span>  
 <span data-ttu-id="b7fa4-277">집합 연산 DbUnionAllExpression, DbExceptExpression 및 DbIntersectExpression은 VisitSetOpExpression 메서드를 통해 처리되며</span><span class="sxs-lookup"><span data-stu-id="b7fa4-277">The set operations DbUnionAllExpression, DbExceptExpression, and DbIntersectExpression are processed by the method VisitSetOpExpression.</span></span> <span data-ttu-id="b7fa4-278">모양의 SqlBuilder를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-278">It creates a SqlBuilder of the shape</span></span>  
  
```xml  
<leftSqlSelectStatement> <setOp> <rightSqlSelectStatement>  
```  
  
 <span data-ttu-id="b7fa4-279">여기서 \<leftSqlSelectStatement > 및 \<rightSqlSelectStatement > 각 입력을 방문 하 여 가져온 Sqlselectstatement는 및 \<setOp >는 해당 작업 (UNION ALL 예:).</span><span class="sxs-lookup"><span data-stu-id="b7fa4-279">Where \<leftSqlSelectStatement> and \<rightSqlSelectStatement> are SqlSelectStatements obtained by visiting each of the inputs, and \<setOp> is the corresponding operation (UNION ALL for example).</span></span>  
  
### <a name="dbscanexpression"></a><span data-ttu-id="b7fa4-280">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-280">DbScanExpression</span></span>  
 <span data-ttu-id="b7fa4-281">다른 조인의 왼쪽 자식인 조인에 대한 입력으로 조인 컨텍스트에서 방문되는 경우 DbScanExpression은 정의 쿼리, 테이블 또는 뷰인 해당 대상의 대상 SQL과 함께 SqlBuilder를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-281">If visited in a join context (as an input to a join that is a left child of another join), DbScanExpression returns a SqlBuilder with the target SQL for the corresponding target, which is either a defining query, table, or a view.</span></span> <span data-ttu-id="b7fa4-282">그렇지 않은 경우에는 해당 대상과 일치하도록 FROM 필드가 설정되어 새 SqlSelectStatement가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-282">Otherwise, a new SqlSelectStatement is created with the FROM field set to correspond to the corresponding target.</span></span>  
  
### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="b7fa4-283">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-283">DbVariableReferenceExpression</span></span>  
 <span data-ttu-id="b7fa4-284">DbVariableReferenceExpression을 방문하면 기호 테이블의 조회에 따라 해당 변수 참조 식에 해당하는 기호가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-284">The visit of a DbVariableReferenceExpression returns the Symbol corresponding to that variable reference expression based on a look up in the symbol table.</span></span>  
  
### <a name="dbpropertyexpression"></a><span data-ttu-id="b7fa4-285">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-285">DbPropertyExpression</span></span>  
 <span data-ttu-id="b7fa4-286">DbPropertyExpression을 방문할 때 조인 별칭 평면화가 식별되고 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-286">Join alias flattening is identified and processed when visiting a DbPropertyExpression.</span></span>  
  
 <span data-ttu-id="b7fa4-287">Instance 속성이 먼저 방문되고 결과는 Symbol, JoinSymbol 또는 SymbolPair입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-287">The Instance property is first visited and the result is a Symbol, a JoinSymbol, or a SymbolPair.</span></span> <span data-ttu-id="b7fa4-288">이러한 세 경우가 처리되는 방식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-288">Here is how these three cases are handled:</span></span>  
  
-   <span data-ttu-id="b7fa4-289">JoinSymbol이 반환되는 경우 필요한 속성의 기호가 NameToExtent 속성에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-289">If a JoinSymbol is returned, than its NameToExtent property contains a symbol for the needed property.</span></span> <span data-ttu-id="b7fa4-290">조인 기호가 중첩 조인을 나타내면 새 기호 쌍이 인스턴스 별칭으로 사용될 기호를 추적하기 위한 조인 기호 및 이후 확인을 위한 실제 속성을 나타내는 기호와 함께 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-290">If the join symbol represents a nested join, a new Symbol pair is returned with the join symbol to track the symbol that would be used as the instance alias, and the symbol representing the actual property for further resolving.</span></span>  
  
-   <span data-ttu-id="b7fa4-291">SymbolPair가 반환되고 Column 부분이 조인 기호인 경우 조인 기호가 다시 반환되지만 이제 열 속성이 현재 속성 식이 나타내는 속성을 가리키도록 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-291">If a SymbolPair is returned and the Column part is a join symbol, a join symbol is again returned, but now the column property is updated to point to the property represented by the current property expression.</span></span> <span data-ttu-id="b7fa4-292">그렇지 않은 경우에는 SqlBuilder가 별칭인 SymbolPair 원본 및 열인 현재 속성의 기호와 함께 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-292">Otherwise a SqlBuilder is returned with the SymbolPair source as the alias, and the symbol for the current property as the column.</span></span>  
  
-   <span data-ttu-id="b7fa4-293">기호가 반환되면 Visit 메서드에서 별칭인 해당 인스턴스 및 열 이름인 속성 이름과 함께 SqlBuilder 메서드를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-293">If a Symbol is returned, the Visit method returns a SqlBuilder method with that instance as the alias, and the property name as column name.</span></span>  
  
### <a name="dbnewinstanceexpression"></a><span data-ttu-id="b7fa4-294">DbNewInstanceExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-294">DbNewInstanceExpression</span></span>  
 <span data-ttu-id="b7fa4-295">DbProjectExpression의 Projection 속성으로 사용되는 경우 DbNewInstanceExpression은 프로젝션된 열을 나타내는 인수의 쉼표로 구분된 목록을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-295">When used as the Projection property of DbProjectExpression, DbNewInstanceExpression produces a comma-separated list of the arguments to represent the projected columns.</span></span>  
  
 <span data-ttu-id="b7fa4-296">DbNewInstanceExpression이 컬렉션 반환 형식을 포함하고 인수로 제공되는 식의 새 컬렉션을 정의하는 경우 다음 세 경우가 별도로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-296">When DbNewInstanceExpression has a collection return type, and defines a new collection of the expressions provided as arguments, the following three cases are handled separately:</span></span>  
  
-   <span data-ttu-id="b7fa4-297">DbNewInstanceExpression이 DbElementExpression을 유일한 인수로 포함하는 경우 다음과 같이 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-297">If DbNewInstanceExpression has DbElementExpression as the only argument, it is translated as follows:</span></span>  
  
    ```  
    NewInstance(Element(X)) =>  SELECT TOP 1 …FROM X  
    ```  
  
 <span data-ttu-id="b7fa4-298">DbNewInstanceExpression이 인수를 포함하지 않는 경우(빈 테이블을 나타냄) 다음과 같이 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-298">If DbNewInstanceExpression has no arguments (represents an empty table), DbNewInstanceExpression is translated into:</span></span>  
  
```  
SELECT CAST(NULL AS <primitiveType>) as X  
FROM (SELECT 1) AS Y WHERE 1=0  
```  
  
 <span data-ttu-id="b7fa4-299">위의 두 경우에 해당하지 않으면 DbNewInstanceExpression은 인수의 UNION ALL 사다리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-299">Otherwise DbNewInstanceExpression builds a union-all ladder of the arguments:</span></span>  
  
```  
SELECT <visit-result-arg1> as X  
UNION ALL SELECT <visit-result-arg2> as X  
UNION ALL …  
UNION ALL SELECT <visit-result-argN> as X  
```  
  
### <a name="dbfunctionexpression"></a><span data-ttu-id="b7fa4-300">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-300">DbFunctionExpression</span></span>  
 <span data-ttu-id="b7fa4-301">정식 함수와 기본 제공 함수는 동일한 방식으로 처리됩니다. 이러한 함수에 특수 처리(TRIM(string), LTRIM(RTRIM(string) 등)가 필요하면 적절한 처리기가 호출되고,</span><span class="sxs-lookup"><span data-stu-id="b7fa4-301">Canonical and built-in functions are processed the same way: if they need special handling (TRIM(string) to  LTRIM(RTRIM(string), for example), the appropriate handler is invoked.</span></span> <span data-ttu-id="b7fa4-302">그렇지 않으면 FunctionName(arg1, arg2, ..., argn)으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-302">Otherwise they are translated to FunctionName(arg1, arg2, ..., argn).</span></span>  
  
 <span data-ttu-id="b7fa4-303">특수 처리와 적절한 처리기가 필요한 함수를 추적하기 위해 사전이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-303">Dictionaries are used to keep track of which functions need special handling and their appropriate handlers.</span></span>  
  
 <span data-ttu-id="b7fa4-304">사용자 정의 함수는 NamespaceName.FunctionName(arg1, arg2, ..., argn)으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-304">User-defined functions are tanslated to NamespaceName.FunctionName(arg1, arg2, ..., argn).</span></span>  
  
### <a name="dbelementexpression"></a><span data-ttu-id="b7fa4-305">DbElementExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-305">DbElementExpression</span></span>  
 <span data-ttu-id="b7fa4-306">DbElementExpression을 방문하는 메서드는 스칼라 하위 쿼리를 나타내는 데 사용되는 경우 DbElementExpression을 방문하기 위해서만 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-306">The method that visits DbElementExpression is only invoked for visiting a DbElementExpression when used to represent a scalar subquery.</span></span> <span data-ttu-id="b7fa4-307">따라서 DbElementExpression은 완전한 SqlSelectStatement로 변환되며 주위에 대괄호를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-307">Therefore, DbElementExpression translates into a complete SqlSelectStatement and adds brackets around it.</span></span>  
  
### <a name="dbquantifierexpression"></a><span data-ttu-id="b7fa4-308">DbQuantifierExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-308">DbQuantifierExpression</span></span>  
 <span data-ttu-id="b7fa4-309">식 형식(Any 또는 All)에 따라 DbQuantifierExpression은 다음과 같이 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-309">Depending on the expression type (Any or All), DbQuantifierExpression is translated it as:</span></span>  
  
```  
Any(input, x) => Exists(Filter(input,x))  
All(input, x) => Not Exists(Filter(input, not(x))  
```  
  
### <a name="dbnotexpression"></a><span data-ttu-id="b7fa4-310">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-310">DbNotExpression</span></span>  
 <span data-ttu-id="b7fa4-311">경우에 따라 입력 식을 사용하여 DbNotExpression의 변환을 축소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-311">In some cases it is possible to collapse the translation of DbNotExpression with its input expression.</span></span> <span data-ttu-id="b7fa4-312">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-312">For example:</span></span>  
  
```  
Not(IsNull(a)) =>  "a IS NOT NULL"  
Not(All(input, x) => Not (Not Exists(Filter(input, not(x))) => Exists(Filter(input, not(x))  
```  
  
 <span data-ttu-id="b7fa4-313">두 번째 축소가 수행되는 이유는 All 형식의 DbQuantifierExpression을 변환할 때 공급자로 인해 발생하는 비효율성 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-313">The reason the second collapse is performed is because inefficiencies were introduced by the provider when translating DbQuantifierExpression of type All.</span></span> <span data-ttu-id="b7fa4-314">따라서 Entity Framework에서 단순화를 수행하지 않았을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-314">Thus the Entity Framework could not have done the simplification.</span></span>  
  
### <a name="dbisemptyexpression"></a><span data-ttu-id="b7fa4-315">DbIsEmptyExpression</span><span class="sxs-lookup"><span data-stu-id="b7fa4-315">DbIsEmptyExpression</span></span>  
 <span data-ttu-id="b7fa4-316">DbIsEmptyExpression은 다음과 같이 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-316">DbIsEmptyExpression is translated as:</span></span>  
  
```  
IsEmpty(inut) = Not Exists(input)  
```  
  
## <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="b7fa4-317">SQL 생성의 두 번째 단계: 문자열 명령 생성</span><span class="sxs-lookup"><span data-stu-id="b7fa4-317">Second Phase of SQL Generation: Generating the String Command</span></span>  
 <span data-ttu-id="b7fa4-318">문자열 SQL 명령을 생성할 때 SqlSelectStatement는 기호의 실제 별칭을 생성합니다. 이를 통해 열 이름 및 익스텐트 별칭 이름 바꾸기 문제가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-318">When generating a string SQL command, the SqlSelectStatement produces actual aliases for the symbols, which addresses the issue of column name and extent alias renaming.</span></span>  
  
 <span data-ttu-id="b7fa4-319">익스텐트 별칭 이름 바꾸기는 SqlSelectStatement 개체를 문자열에 쓰는 동안 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-319">Extent alias renaming occurs while writing the SqlSelectStatement object into a string.</span></span> <span data-ttu-id="b7fa4-320">먼저 외부 익스텐트에서 사용하는 모든 별칭의 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-320">First create a list of all the aliases used by the outer extents.</span></span> <span data-ttu-id="b7fa4-321">FromExtents(또는 null이 아닌 경우 AllJoinExtents)의 각 기호가 외부 익스텐트와 충돌하면 해당 기호의 이름이 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-321">Each symbol in the FromExtents (or AllJoinExtents if it is non-null), gets renamed if it collides with any of the outer extents.</span></span> <span data-ttu-id="b7fa4-322">이름을 바꿔야 하는 경우 AllExtentNames에서 수집된 모든 익스텐트와 충돌하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-322">If renaming is needed, it will not conflict with any of the extents collected in AllExtentNames.</span></span>  
  
 <span data-ttu-id="b7fa4-323">열 이름 바꾸기는 Symbol 개체를 문자열에 쓰는 동안 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-323">Column renaming occurs while writing a Symbol object to a string.</span></span> <span data-ttu-id="b7fa4-324">첫 번째 단계의 AddDefaultColumns는 특정 열 기호의 이름을 바꿔야 하는지 여부를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-324">AddDefaultColumns in the first phase has determined if a certain column symbol has to be renamed.</span></span> <span data-ttu-id="b7fa4-325">두 번째 단계에서는 생성된 이름이 AllColumnNames에서 사용되는 모든 이름과 충돌하지 않도록 하기 위해서만 이름 바꾸기가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-325">In the second phase only the rename occurs making sure that the name produced does not conflict with any name used in AllColumnNames</span></span>  
  
 <span data-ttu-id="b7fa4-326">익스텐트 별칭과 열에 고유한 이름을 생성하려면 <existing_name>_n을 사용합니다. 여기서 n은 아직 사용되지 않은 가장 작은 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-326">To produce unique names both for extent aliases and for columns, use <existing_name>_n where n is the smallest alias that has not been used yet.</span></span> <span data-ttu-id="b7fa4-327">모든 별칭의 전역 목록을 사용하면 연속된 이름 바꾸기의 필요성이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="b7fa4-327">The global list of all aliases increases the need for cascading renames.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7fa4-328">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7fa4-328">See Also</span></span>  
 [<span data-ttu-id="b7fa4-329">샘플 공급자의 SQL 생성</span><span class="sxs-lookup"><span data-stu-id="b7fa4-329">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)
