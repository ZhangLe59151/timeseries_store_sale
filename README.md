# timeseries_store_sale
store sale amount of one country different stores and categories

##### Kaggle Task:   
https://www.kaggle.com/competitions/store-sales-time-series-forecasting   
   
##### pypi website:   
https://pypi.org/project/timeseries-store-sale/   
   
##### documentation:
     

#### quick start 
1. install from pypi   
```
pip install timeseries-store-sale
```
2. generate training data:   
```
s = TimeSeriesDataLoader()

# get train data loader
start_date = '2013-01-01'
end_data = '2017-01-01'

data_path = {
            'main': './train.csv',
            'oil': './oil.csv',
            'holiday': './holidays_events.csv',
            'transaction': './transactions.csv',
            'store': './stores.csv'
        }

s.update_param(store_arr=None, family_arr=None, data_path=data_path)
s.prepare_data()
s.get_datasets(start_date, end_data)
s.get_data_loader(True)
train_dataloader = s.data_loader
   
start_date = '2017-01-01'
end_data = '2018-01-01'


s.get_datasets(start_date, end_data)
s.get_data_loader(False)
valid_dataloader = s.data_loader
len(s.data_loader), len(s.data_loader.dataset)
```
3. tran
```
o = TrainLSTM(True)
o.update_pramas(input_size = 26, num_epochs=35)
o.train(train_dataloader, valid_dataloader)
o.save_model('model_name.pt', o.model)
```
