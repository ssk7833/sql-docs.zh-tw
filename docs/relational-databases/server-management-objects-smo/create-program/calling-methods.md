---
title: "呼叫方法 |Microsoft 文件"
ms.custom: 
ms.date: 08/06/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: smo
ms.reviewer: 
ms.suite: sql
ms.technology: docset-sql-devref
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- methods [SMO]
- calling methods
- SQL Server Management Objects, method calling
- SMO [SQL Server], method calling
ms.assetid: c88d5c5f-9ff0-4f84-b2b6-24c6b90fa15e
caps.latest.revision: "46"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: Inactive
ms.openlocfilehash: 6e1c30acae15e0f1d15e5cabc426468221b419a4
ms.sourcegitcommit: 44cd5c651488b5296fb679f6d43f50d068339a27
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/17/2017
---
# <a name="calling-methods"></a>呼叫方法
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)]方法會執行特定工作相關的物件，例如發出**檢查點**資料庫或要求執行個體的登入的列舉的清單上[!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。  
  
 方法會在物件上執行作業。 方法可以採用參數，而且通常有一個傳回值。 傳回值可以是簡單資料類型、複雜物件，或包含許多成員的結構。  
  
 使用例外狀況處理來偵測方法是否成功。 如需詳細資訊，請參閱[Handling SMO Exceptions](../../../relational-databases/server-management-objects-smo/create-program/handling-smo-exceptions.md)。  
  
## <a name="examples"></a>範例  
如果要使用所提供的任何程式碼範例，您必須選擇建立應用程式用的程式設計環境、程式設計範本，及程式設計語言。 如需詳細資訊，請參閱[建立 Visual C# 35。在 Visual Studio.NET 中的 SMO 專案](../../../relational-databases/server-management-objects-smo/how-to-create-a-visual-csharp-smo-project-in-visual-studio-net.md)。  
 
  
## <a name="using-a-simple-smo-method-in-visual-basic"></a>在 Visual Basic 中使用簡單 SMO 方法  
 在此範例中，<xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> 方法不會採用任何參數，而且沒有傳回值。  
  
```VBNET
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server
'Define a Database object variable by supplying the parent server and the database name arguments in the constructor.
Dim db As Database
db = New Database(srv, "Test_SMO_Database")
'Call the Create method to create the database on the instance of SQL Server. 
db.Create()
```
  
## <a name="using-a-simple-smo-method-in-visual-c"></a>在 Visual C# 中使用簡單 SMO 方法  
 在此範例中，<xref:Microsoft.SqlServer.Management.Smo.Database.Create%2A> 方法不會採用任何參數，而且沒有傳回值。  
  
```csharp  
{   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Define a Database object variable by supplying the parent server and the database name arguments in the constructor.   
Database db;   
db = new Database(srv, "Test_SMO_Database");   
//Call the Create method to create the database on the instance of SQL Server.   
db.Create();   
```  
  
 }  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-basic"></a>在 Visual Basic 中搭配參數使用 SMO 方法  
 <xref:Microsoft.SqlServer.Management.Smo.Table>物件具有方法呼叫<xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>。 此方法需要指定 **FillFactor**的數值參數。  
  
```VBNET
Dim srv As Server  
srv = New Server  
Dim tb As Table  
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources")  
tb.RebuildIndexes(70)  
```  
  
## <a name="using-an-smo-method-with-a-parameter-in-visual-c"></a>在 Visual C# 中搭配參數使用 SMO 方法  
 <xref:Microsoft.SqlServer.Management.Smo.Table>物件具有方法呼叫<xref:Microsoft.SqlServer.Management.Smo.Table.RebuildIndexes%2A>。 此方法需要指定 `FillFactor`的數值參數。  
  
```csharp  
{   
Server srv = default(Server);   
srv = new Server();   
Table tb = default(Table);   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
}   
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-basic"></a>在 Visual Basic 中使用傳回 DataTable 物件的列舉方法  
 本章節描述如何呼叫列舉方法，以及如何處理中傳回的資料<xref:System.Data.DataTable>物件。  
  
 <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A> 方法會傳回 <xref:System.Data.DataTable> 物件，此物件需要進一步導覽，才能存取有關 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] 執行個體的所有可用定序資訊。  
  
```VBNET
'Connect to the local, default instance of SQL Server.  
Dim srv As Server  
srv = New Server  
'Call the EnumCollations method and return collation information to DataTable variable.  
Dim d As DataTable  
'Select the returned data into an array of DataRow.  
d = srv.EnumCollations  
'Iterate through the rows and display collation details for the instance of SQL Server.  
Dim r As DataRow  
Dim c As DataColumn  
For Each r In d.Rows  
    Console.WriteLine("==")  
    For Each c In r.Table.Columns  
        Console.WriteLine(c.ColumnName + " = " + r(c).ToString)  
    Next  
Next  
```  
  
## <a name="using-an-enumeration-method-that-returns-a-datatable-object-in-visual-c"></a>在 Visual C# 中使用傳回 DataTable 物件的列舉方法  
 本章節描述如何呼叫列舉方法，以及如何處理中傳回的資料<xref:System.Data.DataTable>物件。  
  
 <xref:Microsoft.SqlServer.Management.Smo.Server.EnumCollations%2A>方法會傳回系統<xref:System.Data.DataTable>物件。 <xref:System.Data.DataTable>物件需要進一步導覽，才能存取的執行個體相關的所有可用定序資訊[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。  
  
```csharp  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumCollations;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=========");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="constructing-an-object-in-visual-basic"></a>在 Visual Basic 中建構物件  
 任何物件的建構函式都可以使用 **New** 運算子來呼叫。 <xref:Microsoft.SqlServer.Management.Smo.Database> 物件建構函式會超載，而範例中所使用的 <xref:Microsoft.SqlServer.Management.Smo.Database> 物件建構函式版本會採用兩個參數：資料庫所屬的 <xref:Microsoft.SqlServer.Management.Smo.Server> 父物件，以及代表新資料庫名稱的字串。  
  
```VBNET
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server
'Declare and define a Database object by supplying the parent server and the database name arguments in the constructor.
Dim d As Database
d = New Database(srv, "Test_SMO_Database")
'Create the database on the instance of SQL Server.
d.Create()
Console.WriteLine(d.Name)
```
  
## <a name="constructing-an-object-in-visual-c"></a>在 Visual C# 中建構物件  
 任何物件的建構函式都可以使用 **New** 運算子來呼叫。 <xref:Microsoft.SqlServer.Management.Smo.Database> 物件建構函式會超載，而範例中所使用的 <xref:Microsoft.SqlServer.Management.Smo.Database> 物件建構函式版本會採用兩個參數：資料庫所屬的 <xref:Microsoft.SqlServer.Management.Smo.Server> 父物件，以及代表新資料庫名稱的字串。  
  
```csharp  
{   
Server srv;   
srv = new Server();   
Table tb;   
tb = srv.Databases("AdventureWorks2012").Tables("Employee", "HumanResources");   
tb.RebuildIndexes(70);   
//Connect to the local, default instance of SQL Server.   
Server srv;   
srv = new Server();   
//Declare and define a Database object by supplying the parent server and the database name arguments in the constructor.   
Database d;   
d = new Database(srv, "Test_SMO_Database");   
//Create the database on the instance of SQL Server.   
d.Create();   
Console.WriteLine(d.Name);   
}  
```  
  
## <a name="copying-an-smo-object-in-visual-basic"></a>在 Visual Basic 中複製 SMO 物件  
 這個程式碼範例會使用<xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A>方法來建立一份<xref:Microsoft.SqlServer.Management.Smo.Server>物件。 <xref:Microsoft.SqlServer.Management.Smo.Server>物件代表的執行個體的連接[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。  
  
```VBNET  
'Connect to the local, default instance of SQL Server.
Dim srv1 As Server
srv1 = New Server()
'Modify the default database and the timeout period for the connection.
srv1.ConnectionContext.DatabaseName = "AdventureWorks2012"
srv1.ConnectionContext.ConnectTimeout = 30
'Make a second connection using a copy of the ConnectionContext property and verify settings.
Dim srv2 As Server
srv2 = New Server(srv1.ConnectionContext.Copy)
Console.WriteLine(srv2.ConnectionContext.ConnectTimeout.ToString)
```
  
## <a name="copying-an-smo-object-in-visual-c"></a>在 Visual C# 中複製 SMO 物件  
 這個程式碼範例會使用<xref:Microsoft.SqlServer.Management.Common.ServerConnection.Copy%2A>方法來建立一份<xref:Microsoft.SqlServer.Management.Smo.Server>物件。 <xref:Microsoft.SqlServer.Management.Smo.Server>物件代表的執行個體的連接[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]。  
  
```csharp  
{   
//Connect to the local, default instance of SQL Server.   
Server srv1;   
srv1 = new Server();   
//Modify the default database and the timeout period for the connection.   
srv1.ConnectionContext.DatabaseName = "AdventureWorks2012";   
srv1.ConnectionContext.ConnectTimeout = 30;   
//Make a second connection using a copy of the ConnectionContext property and verify settings.   
Server srv2;   
srv2 = new Server(srv1.ConnectionContext.Copy);   
Console.WriteLine(srv2.ConnectionContext.ConnectTimeout.ToString);   
}  
```  
  
## <a name="monitoring-server-processes-in-visual-basic"></a>在 Visual Basic 中監視伺服器處理序  
 您可以取得目前的狀態類型資訊的執行個體的相關[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]透過列舉方法。 程式碼範例會使用 <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> 方法來探索目前處理序的相關資訊。 該範例也會示範如何使用傳回之 <xref:System.Data.DataTable> 物件中的資料行和資料列。  
  
```VBNET
'Connect to the local, default instance of SQL Server.
Dim srv As Server
srv = New Server
'Call the EnumCollations method and return collation information to DataTable variable.
Dim d As DataTable
'Select the returned data into an array of DataRow.
d = srv.EnumProcesses
'Iterate through the rows and display collation details for the instance of SQL Server.
Dim r As DataRow
Dim c As DataColumn
For Each r In d.Rows
    Console.WriteLine("============================================")
    For Each c In r.Table.Columns
        Console.WriteLine(c.ColumnName + " = " + r(c).ToString)
    Next
Next
```
  
## <a name="monitoring-server-processes-in-visual-c"></a>在 Visual C# 中監視伺服器處理序  
 您可以取得目前的狀態類型資訊的執行個體的相關[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]透過列舉方法。 程式碼範例會使用 <xref:Microsoft.SqlServer.Management.Smo.Server.EnumProcesses%2A> 方法來探索目前處理序的相關資訊。 該範例也會示範如何使用傳回之 <xref:System.Data.DataTable> 物件中的資料行和資料列。  
  
```csharp  
//Connect to the local, default instance of SQL Server.   
{   
Server srv = default(Server);   
srv = new Server();   
//Call the EnumCollations method and return collation information to DataTable variable.   
DataTable d = default(DataTable);   
//Select the returned data into an array of DataRow.   
d = srv.EnumProcesses;   
//Iterate through the rows and display collation details for the instance of SQL Server.   
DataRow r = default(DataRow);   
DataColumn c = default(DataColumn);   
foreach ( r in d.Rows) {   
  Console.WriteLine("=====");   
  foreach ( c in r.Table.Columns) {   
    Console.WriteLine(c.ColumnName + " = " + r(c).ToString);   
  }   
}   
}   
```  
  
## <a name="see-also"></a>請參閱＜  
 <xref:Microsoft.SqlServer.Management.Smo.Server>   
 <xref:Microsoft.SqlServer.Management.Common.ServerConnection>  
  
  