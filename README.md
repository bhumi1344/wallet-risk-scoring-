# wallet-risk-scoring-from-scratch

DATA COLLECTION METHOD:
• Primary Sources: Etherscan API for comprehensive transaction data
• Transaction Types: Regular ETH transactions, ERC20 transfers, internal calls
• Compound Focus: Filtered interactions with Compound V2/V3 protocols
• Coverage: Complete transaction history per wallet address
    
FEATURE SELECTION RATIONALE:
1. TEMPORAL FEATURES:
       • Account Age: Newer accounts = higher risk
       • Transaction Frequency: Extreme patterns indicate risk
       • Activity Consistency: Sporadic behavior flagged
    
2. TRANSACTION QUALITY:
       • Failed Transaction Rate: Poor execution planning
       • Gas Efficiency: Technical competence indicator
       • Transaction Size: Large movements = higher exposure
    
3. COMPOUND-SPECIFIC FEATURES:
       • Supply/Borrow Ratios: Leverage analysis
       • Liquidation Events: Direct risk evidence
       • Protocol Interaction Depth: Diversification measure
    
4. BEHAVIORAL INDICATORS:
       • High-Frequency Patterns: Bot/MEV detection
       • Contract Diversification: Concentration risk
       • Volume Patterns: Whale behavior analysis
    
SCORING METHOD (0-1000 SCALE):
Risk Component Breakdown:
    • Account Age Risk: 0-100 points
    • Transaction Frequency: 0-100 points  
    • Failed Transactions: 0-80 points
    • Large Transactions: 0-120 points
    • Liquidation Events: 0-200 points
    • Leverage Risk: 0-150 points
    • High-Frequency Trading: 0-100 points
    • Gas Efficiency: 0-50 points
    • Diversification: 0-60 points
    • Compound Interaction: 0-40 points
    
RISK INDICATORS JUSTIFICATION:
HIGH-RISK INDICATORS:
    • Recent account creation (< 30 days)
    • Liquidation events (direct risk evidence)
    • High leverage ratios (> 2x)
    • Failed transaction patterns (> 10%)
    • Extreme activity patterns (> 50 tx/day or < 1/week)
    
MEDIUM-RISK INDICATORS:
    • Moderate leverage (1-2x)
    • Large transaction volumes (> 100 ETH)
    • Limited diversification
    • Gas inefficiency patterns
    
LOW-RISK INDICATORS:
    • Long account history (> 1 year)
    • Consistent activity patterns
    • Balanced protocol usage
    • Efficient gas usage
    • No liquidation history
    
MODEL SCALABILITY:
    • Batch processing with rate limiting
    • Modular feature extraction
    • Configurable scoring weights
    • Comprehensive error handling
    • Intermediate result saving
    
VALIDATION APPROACH:
    • Historical liquidation events as ground truth
    • Statistical distribution analysis
    • Cross-validation with known addresses
    • Expert domain knowledge integration
