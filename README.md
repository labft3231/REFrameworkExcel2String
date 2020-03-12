# REFramaworkExcel2String


### - Excel 데이터(datatable)를 읽어 String으로 활용하기


#### 시작하기 전 바꿔야할 부분
TransactionItem은 기본적으로 QueueItem datatype을 가지고 있다. 이를 String으로 활용하기 위해서 메인에서 
datatype을 String으로 하나하나 바꿔준 후 오류가 나는 부분을 하나하나 바꿔줘야한다. 앞에 말한거 처럼 Queue로 
되어 있기 때문에 기본적으로 큐 데이터를 읽어온다든가 큐를 활용한 것들은 그냥 주석처리(ctrl + d) 하거나 
지워버리면 된다. 


#### 1. GetTransactionData
```
 - TransactionNumber가 1인 경우는 트랜젝션이 처음 도는 경우이다. 프로젝트를 처음 intialize할때 데이터를 저장해도
 되지만 여기서 해도 상관없다.
 - Excel 파일을 읽어 DataTable을 가져온다.
 - DataTable의 .Rows.Item(in_TransactionNumber-1).ToString 을 통해 String type의 TransactionItem에 저장해준다.
 - 현재의 트랜젝션 번호인 TransactionNumber 값 보다 가져온 DataTable의 row 수가 작다면 out_Transaction을 
 .Rows.Item(in_TransactionNumber-1).ToString 으로 크다면 datatable을 넘어섰다는 의미가 되므로 out_transaction은 
 할게 없으니 Nothing으로 바꿔준다.
```

#### 2. Process
```
 - in_TransactionItem string 이므로 상황에 맞는 data type으로 가공하여 그냥 쓰면 된다.
```
 
