# DBMS_Projects
create DATABASE IF NOT EXISTS
portfolio_db;
USE portfolio_db;

CREATE TABLE portfolio (
    portfolio_id INT PRIMARY KEY AUTO_INCREMENT,
    user_name VARCHAR(50),
    total_value DECIMAL(10,2)
);

CREATE TABLE asset (
    asset_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50),
    type VARCHAR(50),
    market_price DECIMAL(10,2)
);

CREATE TABLE investment (
    investment_id INT PRIMARY KEY AUTO_INCREMENT,
    portfolio_id INT,
    asset_id INT,
    quantity INT,
    purchase_price DECIMAL(10,2),
    FOREIGN KEY (portfolio_id) REFERENCES portfolio(portfolio_id),
    FOREIGN KEY (asset_id) REFERENCES asset(asset_id)
);

CREATE TABLE transaction (
    transaction_id INT PRIMARY KEY AUTO_INCREMENT,
    investment_id INT,
    type VARCHAR(10),
    amount DECIMAL(10,2),
    date DATE,
    FOREIGN KEY (investment_id) REFERENCES investment(investment_id)
);

-- Sample Data
INSERT INTO portfolio (user_name, total_value) VALUES ('Aditya', 0);

INSERT INTO asset (name, type, market_price) VALUES 
('Stock A', 'Stock', 100),
('Gold', 'Commodity', 5000);

INSERT INTO investment (portfolio_id, asset_id, quantity, purchase_price) VALUES 
(1,1,10,90),
(1,2,2,4500);

INSERT INTO transaction (investment_id, type, amount, date) VALUES 
(1,'BUY',900,'2024-01-01'),
(2,'BUY',9000,'2024-02-01');

SELECT * FROM portfolio;
SELECT * FROM asset;
SELECT * FROM investment;
