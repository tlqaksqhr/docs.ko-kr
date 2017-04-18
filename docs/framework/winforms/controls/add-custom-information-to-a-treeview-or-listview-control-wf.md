---
title: "방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ListItem"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "예제[Windows Forms], ListView 컨트롤"
  - "예제[Windows Forms], TreeView 컨트롤"
  - "ListView 컨트롤[Windows Forms], 사용자 지정 정보 추가"
  - "Tag 속성"
  - "TreeView 컨트롤[Windows Forms], 사용자 지정 정보 추가"
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# 방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)
Windows Forms <xref:System.Windows.Forms.TreeView> 컨트롤에서 파생 노드를 만들거나 <xref:System.Windows.Forms.ListView> 컨트롤에서 파생 항목을 만들 수 있습니다.  파생 기능을 사용하면 필요한 모든 필드뿐만 아니라 이 필드를 처리하는 사용자 지정 메서드와 생성자를 추가할 수 있습니다.  이 기능을 사용하여 Customer 개체를 각 트리 노드나 목록 항목에 추가할 수도 있습니다.  다음은 <xref:System.Windows.Forms.TreeView> 컨트롤에 대한 예제이지만 <xref:System.Windows.Forms.ListView> 컨트롤에도 같은 방법을 사용할 수 있습니다.  
  
### 트리 노드를 파생시키려면  
  
-   <xref:System.Windows.Forms.TreeNode> 클래스에서 파일 경로를 기록할 사용자 지정 필드를 포함하는 새 노드 클래스를 파생시킵니다.  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### 파생된 트리 노드를 사용하려면  
  
1.  파생된 새 트리 노드를 함수 호출에 대한 매개 변수로 사용할 수 있습니다.  
  
     아래 예제에서는 내 문서 폴더가 텍스트 파일의 위치로 설정되었습니다.  Windows 운영 체제가 실행되는 대부분의 컴퓨터에는 내 문서 폴더가 포함되어 있으므로 이 위치를 사용합니다.  또한 이 위치를 선택하면 사용자는 최소한의 시스템 액세스 수준으로 응용 프로그램을 안전하게 실행할 수 있습니다.  
  
    ```vb  
    ' You should replace the bold text file   
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
  
    ```  
  
    ```csharp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       + @"\TextFile.txt") );  
  
    ```  
  
    ```cpp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2.  트리 노드를 전달하고 <xref:System.Windows.Forms.TreeNode> 클래스로 형식화한 경우 파생 클래스로 캐스팅해야 합니다.  캐스팅은 개체 형식을 명시적으로 변환하는 것입니다.  캐스팅에 대한 자세한 내용은 [Implicit and Explicit Conversions](../Topic/Implicit%20and%20Explicit%20Conversions%20\(Visual%20Basic\).md)\([!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)]\), [\(\) 연산자](../Topic/\(\)%20Operator%20\(C%23%20Reference\).md)\([!INCLUDE[csprcs](../../../../includes/csprcs-md.md)]\) 또는 [캐스팅 연산자: \(\)](../../../../amples/snippets/visualbasic/VS_Snippets_Wpf/DocumentStructure/visualbasic/spec_withstructure-xps/_rels/.rels)\([!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]\)를 참조하십시오.  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",   
             myNode->FilePath));  
       }  
    ```  
  
## 참고 항목  
 [TreeView 컨트롤](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [ListView 컨트롤](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)