Project Details
This platform allows users to search, bid, and communicate on real estate listings globally. Users interact through web/mobile clients. The platform aggregates data from various third-party sources and enables real-time communication between buyers and sellers.
Architecture Decisions
To ensure high availability and scalability, we chose a multi-region, multi-AZ deployment using AWS. Application services run on ECS or EKS, behind Application Load Balancers. Real-time chat is handled via WebSocket services deployed within the app layer. Media content is served using CloudFront CDN and stored in S3. A managed RDS cluster supports structured queries, and Redis handles caching and session management.
User Load	Compute (ECS/EC2)	RDS/Database	Redis Cache	S3 Storage	Bandwidth (GB)	Est. Monthly Cost
100 concurrent	$50	$30	$10	$10	50	~$100
10,000 concurrent	$2,000	$700	$300	$500	2,000	~$3,500
100,000 concurrent	$10,000	$3,000	$1,500	$2,500	10,000	~$17,000
100k monthly	$500	$100	$50	$50	200	~$700
1M monthly	$5,000	$700	$300	$1,000	5,000	~$7,500
100M monthly	$200,000	$50,000	$30,000	$50,000	1,000,000	~$330,000
________________________________________
4. Cost Estimation Table
User Load	Compute (ECS/EC2)	RDS/Database	Redis Cache	S3 Storage	Bandwidth (GB)	Est. Monthly Cost
100 concurrent	$50	$30	$10	$10	50	~$100
10,000 concurrent	$2,000	$700	$300	$500	2,000	~$3,500
100,000 concurrent	$10,000	$3,000	$1,500	$2,500	10,000	~$17,000
100k monthly	$500	$100	$50	$50	200	~$700
1M monthly	$5,000	$700	$300	$1,000	5,000	~$7,500
100M monthly	$200,000	$50,000	$30,000	$50,000	1,000,000	~$330,000

