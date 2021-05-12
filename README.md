# Assignment2

Here is a single-day scoring file of the daily returns of individual stocks derived from a machine learning model.  
Normally my strategy is to hold the top 200 stocks, but in order to capture sector-neutral alpha, I need to allocate these 200 stocks in proportion to the sectors of the CSI 500 constituents. 
So I wrote a function ind_res4 to sector-bound my positions according to certain laws.  

### Function Parameters 

* d1: String of the current date 
* df_temp: The pd.dataframe for the stock scoring of the current day 
* pool_N: The set of the stocks held before adjustment
* retain: Fuzzy interval parameters, only positions are allowed to be adjusted within the range of scoring top hold_num * (1 + retain)
* hold_num: Number of stock positions
* ind_ceil: Rate of relaxation of industry quantitative restrictions
* ind_sig: "industry", extract the industry field in other_data
* func_pos: Industry code slice parameter, fixed at -6
* max_res_retain: Fuzzy interval parameters, positions are allowed to be adjusted within the range of scoring top hold_num * (1 + retain) * max_res_retain
* ind_limit_days_dict: You can manually control the industry that needs to change the rate, pass in the dictionary key for the industry, values=1 for the constraint, values=0 not constraint.  
