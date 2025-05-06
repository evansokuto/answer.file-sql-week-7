# answer.file-sql-week-7

question 1

-- Create the new 1NF-compliant table
CREATE TABLE ProductDetail_1NF (
    OrderID INT,
    CustomerName VARCHAR(100),
    Product VARCHAR(100)
);

-- Insert normalized data (manual split for this example)
INSERT INTO ProductDetail_1NF VALUES (101, 'John Doe', 'Laptop');
INSERT INTO ProductDetail_1NF VALUES (101, 'John Doe', 'Mouse');
INSERT INTO ProductDetail_1NF VALUES (102, 'Jane Smith', 'Tablet');
INSERT INTO ProductDetail_1NF VALUES (102, 'Jane Smith', 'Keyboard');
INSERT INTO ProductDetail_1NF VALUES (102, 'Jane Smith', 'Mouse');
INSERT INTO ProductDetail_1NF VALUES (103, 'Emily Clark', 'Phone');

question 2

-- Create Orders table
CREATE TABLE Orders (
    OrderID INT PRIMARY KEY,
    CustomerName VARCHAR(100)
);

-- Create OrderDetails table
CREATE TABLE OrderDetails (
    OrderID INT,
    Product VARCHAR(100),
    Quantity INT,
    FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)
);

-- Insert data into Orders
INSERT INTO Orders VALUES (101, 'John Doe');
INSERT INTO Orders VALUES (102, 'Jane Smith');
INSERT INTO Orders VALUES (103, 'Emily Clark');

-- Insert data into OrderDetails
INSERT INTO OrderDetails VALUES (101, 'Laptop', 2);
INSERT INTO OrderDetails VALUES (101, 'Mouse', 1);
INSERT INTO OrderDetails VALUES (102, 'Tablet', 3);
INSERT INTO OrderDetails VALUES (102, 'Keyboard', 1);
INSERT INTO OrderDetails VALUES (102, 'Mouse', 2);
INSERT INTO OrderDetails VALUES (103, 'Phone', 1);
