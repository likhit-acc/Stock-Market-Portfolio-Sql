# Stock-Market-Portfolio-Sql
A MySQL database system to track stock portfolios, transactions, and real-time prices with automated validation
# 📈 Stock Market Portfolio Database  
---

## 🌟 Key Features  
- **Buy/Sell Validation**: Automatically blocks overselling (e.g., selling 100 shares when you own 50).  
- **Real-Time Prices**: Track historical stock prices.  
- **Portfolio Tracking**: See client holdings and average purchase prices.  

## 🛠 Setup (5 Minutes)  
1. **Run in MySQL**:  
   ```sql
   -- Create database and tables
   SOURCE sql/stock_market_portfolio.sql;
   
   -- View sample portfolio
   SELECT * FROM Client_Portfolio;
   ```

---

## 📊 Sample Data  
**Clients**  
| Name              | Email                          |  
|-------------------|--------------------------------|  
| Aradhya Jain      | aradhaya1111@gmail.com         |  
| Naivedhya Parmar  | naivedhya.p@financepro.com     |  

**Stocks**  
| Symbol      | Name                  | Sector      |  
|-------------|-----------------------|-------------|  
| BSE         | Bombay Stock Exchange | Finance     |  
| INFY        | Infosys               | Technology  |  

---

## 💡 Example Queries  
```sql
-- Check portfolio value  
SELECT 
    c.name AS Client,
    s.symbol AS Stock,
    cp.shares * sp.price AS Value
FROM Client_Portfolio cp
JOIN Clients c USING (client_id)
JOIN Stocks s USING (stock_ref)
JOIN Stock_Price sp USING (stock_ref);

-- Recent transactions  
SELECT * FROM Transactions ORDER BY transaction_date DESC LIMIT 5;
```

---

## 🧠 What I Learned  
- **SQL Triggers**: Auto-validate transactions (e.g., block invalid sells).  
- **Database Design**: Structured tables for real-world finance tracking.  
- **Data Integrity**: Used constraints (`CHECK`, `ENUM`) to ensure clean data.  

---

## 📄 License  
MIT License - Feel free to use and modify!  

*Created for my BBA (BFSI) studies – Likhit Kasliwal
