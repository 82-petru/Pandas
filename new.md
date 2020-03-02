daily_sales_replaced = daily_sales.replace(';,;', ';')


daily_sales_splitted = daily_sales_replaced.split(',')

daily_transactions_split = []
for transaction in daily_sales_splitted:
  t = transaction.split(';')
  daily_transactions_split.append(t)
#print(daily_transactions_split)  

daily_transactions_strip = []
for space in daily_transactions_split:
  daily_transaction_strip = []
  for each in space:
    s = each.strip()
    daily_transaction_strip.append(s)
  daily_transactions_strip.append(daily_transaction_strip)
#print(daily_transactions_strip)

customers = []
sales = []
thread_sold = []
for data in daily_transactions_strip:
  customers.append(data[0])
  sales.append(data[1])
  thread_sold.append(data[2])
#print(customers)
#print(sales)
#print(thread_sold)

total_sales = 0
for values in sales:
  total_sales = total_sales + float(values.strip('$'))
#rint(total_sales)
thread_sold_split = []
for single_color in thread_sold:
  for color in single_color.split('&'):
    thread_sold_split.append(color)
#print(thread_sold_split)


def color_count(color):
  total = 0 
  for item in thread_sold_split:
    if color == item:
      total = thread_sold_split.count(item)
  return total
colors =  ['red','yellow','green','white','black','blue','purple']
for color in colors:   
  print("Thread Shed sold {} of {} thread today.".format(color_count(color), color))