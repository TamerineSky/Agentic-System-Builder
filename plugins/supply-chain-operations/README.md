# Supply Chain Operations Plugin

Comprehensive supply chain management plugin providing intelligent agents, methodologies, and workflows for demand forecasting, inventory optimization, logistics planning, supplier management, quality control, and procurement operations.

## Overview

The Supply Chain Operations Plugin enables supply chain professionals to leverage AI-powered analysis and decision support across the end-to-end supply chain. From demand planning and inventory optimization to logistics execution and supplier management, this plugin provides expert guidance, analytical capabilities, and best-practice methodologies.

**Plugin Version**: 1.0.0
**Category**: Business Operations
**Target Users**: Supply chain managers, demand planners, procurement professionals, logistics coordinators, inventory analysts, quality engineers

## Components

### Agents (6)

Specialized AI agents providing domain expertise:

1. **demand-forecaster** (Sonnet) - Expert in demand forecasting using time series, causal, and ML methods
2. **inventory-optimizer** (Sonnet) - Specialist in EOQ, safety stock, and inventory policy optimization
3. **logistics-planner** (Sonnet) - Expert in route optimization, carrier selection, and network design
4. **supplier-relationship-manager** (Sonnet) - Specialist in supplier scorecards, risk assessment, and development
5. **quality-control-analyst** (Haiku) - Expert in SPC, defect analysis, and Six Sigma methodologies
6. **procurement-advisor** (Sonnet) - Specialist in spend analysis, strategic sourcing, and cost optimization

### Skills (10)

Modular knowledge packages with progressive disclosure:

1. **demand-forecasting-methods** - Time series, causal, and ML forecasting techniques
2. **inventory-optimization** - EOQ, safety stock, reorder point calculations
3. **logistics-planning** - Route optimization, carrier selection, consolidation strategies
4. **supplier-scorecards** - Performance measurement and evaluation frameworks
5. **quality-control** - SPC, process capability, and Six Sigma DMAIC
6. **procurement-analysis** - Spend analysis, strategic sourcing, TCO analysis
7. **network-optimization** - Distribution network design and facility location
8. **risk-assessment** - Supply chain risk identification and mitigation
9. **cost-analysis** - Total cost of ownership and cost-to-serve modeling
10. **scor-framework** - SCOR model processes, metrics, and best practices

### Commands (12)

Operational workflows for daily supply chain management:

1. **/demand-forecast** - Generate demand forecast for product line and horizon
2. **/inventory-status** - Current inventory health and turnover analysis
3. **/reorder-calc** - Calculate optimal reorder points and order quantities
4. **/supplier-scorecard** - Generate supplier performance scorecard
5. **/logistics-plan** - Create optimized shipment and routing plan
6. **/quality-analysis** - Quality control analysis with SPC and capability assessment
7. **/procurement-analysis** - Procurement spend and sourcing opportunity analysis
8. **/risk-assessment** - Supply chain risk identification and mitigation planning
9. **/cost-breakdown** - Total cost analysis with optimization recommendations
10. **/stockout-risk** - Stockout risk analysis and mitigation actions
11. **/abc-analysis** - ABC inventory classification and policy recommendations
12. **/lead-time-analysis** - Supplier lead time performance and improvement opportunities

### Orchestrations (5)

Multi-agent workflows for complex supply chain processes:

1. **s-and-op-process.md** - Monthly Sales & Operations Planning cycle (4-week workflow)
2. **new-product-launch.md** - New product supply chain readiness and execution (6-9 month process)
3. **supplier-evaluation.md** - Comprehensive supplier evaluation and selection (4-8 week process)
4. **disruption-response.md** - Rapid supply chain disruption response protocol
5. **quarterly-supply-review.md** - Quarterly supply chain performance review and planning

## Installation

### Prerequisites

- Claude Code with plugin support
- Access to supply chain data sources (ERP, WMS, TMS, supplier portals)
- Familiarity with supply chain concepts and terminology

### Setup

1. Clone or download this plugin to your Claude Code plugins directory:
   ```bash
   cd ~/.claude/plugins
   git clone <repository-url> supply-chain-operations
   ```

2. The plugin will be automatically discovered by Claude Code

3. Verify installation by listing available agents:
   ```
   @demand-forecaster
   ```

## Quick Start

### Example 1: Generate Demand Forecast

```
/demand-forecast "consumer electronics" "12 months"
```

This command will:
- Collect and prepare historical demand data
- Analyze demand patterns (trend, seasonality, variability)
- Select and apply appropriate forecasting methods
- Generate baseline forecast with accuracy metrics
- Incorporate business judgment and market intelligence
- Provide actionable recommendations for inventory planning

### Example 2: Optimize Inventory Policies

```
@inventory-optimizer Calculate optimal reorder points and safety stock for our top 100 SKUs
to achieve 95% service level. Current inventory is excessive.
```

The inventory-optimizer will:
- Analyze current inventory levels and turnover
- Calculate demand variability and lead times
- Determine EOQ and reorder points using service level targets
- Recommend safety stock levels balancing cost and service
- Provide expected inventory reduction and service improvement

### Example 3: Supplier Performance Review

```
/supplier-scorecard "ABC Manufacturing" "Q4 2024"
```

This generates a comprehensive scorecard with:
- Quality metrics (PPM, first pass yield, returns)
- Delivery performance (OTD, OTIF, lead time)
- Cost competitiveness and cost-down achievements
- Responsiveness and collaboration ratings
- Overall weighted score and performance tier
- Improvement recommendations or recognition

### Example 4: Logistics Optimization

```
@logistics-planner We have 150 customer orders to deliver in the northeast region
this week. Optimize our routing and carrier selection to minimize freight costs
while meeting delivery commitments.
```

The logistics-planner will:
- Analyze shipment characteristics and destinations
- Optimize routes for fleet deliveries (VRP)
- Select appropriate carriers and modes (TL, LTL, parcel)
- Identify consolidation opportunities
- Provide detailed shipment plan with cost and service KPIs

## Use Cases

### Demand Planning and Forecasting

- **Monthly demand forecasting**: Generate statistical forecasts using time series methods
- **New product forecasting**: Forecast demand for new products using analogous methods
- **Consensus planning**: Combine statistical forecasts with sales input
- **Forecast accuracy analysis**: Track and improve forecast performance
- **Scenario planning**: Create optimistic, base, and pessimistic demand scenarios

### Inventory Management

- **Inventory optimization**: Calculate optimal order quantities and reorder points
- **Safety stock analysis**: Determine appropriate safety stock by service level
- **ABC/XYZ segmentation**: Classify inventory and apply differentiated policies
- **Excess inventory reduction**: Identify and disposition slow-moving stock
- **Stockout prevention**: Proactively identify and mitigate stockout risks

### Logistics and Transportation

- **Route optimization**: Optimize delivery routes for fleet operations
- **Carrier selection**: Evaluate and select carriers based on cost and service
- **Load consolidation**: Identify opportunities to consolidate LTL to TL
- **Network design**: Design optimal distribution network configuration
- **Freight cost analysis**: Analyze and reduce transportation spend

### Supplier Management

- **Supplier scorecarding**: Measure supplier performance across key dimensions
- **Supplier evaluation**: Comprehensive supplier assessment for sourcing decisions
- **Risk assessment**: Identify and mitigate supplier and supply chain risks
- **Supplier development**: Improve underperforming supplier capabilities
- **Business reviews**: Conduct structured supplier business reviews

### Quality Control

- **SPC implementation**: Set up statistical process control systems
- **Process capability**: Assess process capability (Cp, Cpk) against specifications
- **Defect analysis**: Pareto analysis and root cause investigation
- **Six Sigma projects**: Execute DMAIC improvement initiatives
- **Cost of quality**: Calculate and reduce cost of poor quality

### Procurement and Sourcing

- **Spend analysis**: Analyze procurement spend for savings opportunities
- **Strategic sourcing**: Develop category strategies and conduct RFx processes
- **Should-cost modeling**: Build cost models for price negotiations
- **Total cost analysis**: Calculate TCO beyond unit price
- **Make-vs-buy**: Analyze insource vs. outsource decisions

## Integration Points

### ERP Systems
- SAP (MM, WM, APO, IBP)
- Oracle (Procurement, Inventory, Order Management)
- NetSuite (Inventory, Purchasing, Fulfillment)

### Supply Chain Planning
- Kinaxis RapidResponse
- o9 Solutions
- Blue Yonder (JDA)
- SAP IBP

### Warehouse and Logistics
- WMS: Manhattan, Blue Yonder, Körber
- TMS: Oracle OTM, SAP TM, Manhattan TMS

### Supplier Management
- Ariba (SAP)
- Coupa Supplier Network
- Ivalua

### Quality Management
- ETQ Reliance
- MasterControl
- TrackWise

## Best Practices

### Data Quality
- Cleanse demand history (remove outliers, adjust for promotions)
- Validate supplier performance data accuracy
- Ensure inventory data reconciliation across systems
- Separate constrained sales from true demand

### Collaboration
- Involve cross-functional teams (sales, operations, finance)
- Conduct regular supplier business reviews
- Share forecasts and plans with suppliers early
- Align on metrics and targets across organization

### Continuous Improvement
- Track forecast accuracy and bias metrics monthly
- Review inventory policies quarterly
- Monitor supplier performance trends
- Conduct post-mortems on disruptions and launches
- Update risk assessments regularly

### Decision-Making
- Use data-driven approaches with business judgment
- Quantify trade-offs (cost vs. service, speed vs. inventory)
- Document assumptions and sensitivity analysis
- Balance short-term tactics with long-term strategy

## Supply Chain Metrics

### Key Performance Indicators

**Customer Service**
- Fill rate (>95% target)
- On-time delivery (>95% target)
- On-time in-full (OTIF) (>90% target)
- Perfect order percentage (>95% target)
- Stockout frequency (<5% target)

**Inventory**
- Inventory turnover (4-12× depending on industry)
- Days on hand (30-90 days typical)
- Inventory value and composition
- Excess and obsolete inventory
- Cash-to-cash cycle time

**Cost**
- Total supply chain cost as % of revenue (4-12%)
- Freight cost per unit
- Cost of goods sold (COGS)
- Procurement savings % per year
- Cost of poor quality

**Supplier**
- Supplier on-time delivery (>95%)
- Supplier quality (PPM <100-1000)
- Supplier lead time performance
- Supplier cost competitiveness

**Quality**
- First pass yield (>99%)
- Defect rate / PPM
- Scrap and rework percentage
- Process capability (Cpk >1.33)
- Customer returns and complaints

## Advanced Topics

### Multi-Echelon Inventory Optimization (MEIO)
Optimize inventory across multi-tier networks (plant → regional DC → local warehouse) to minimize total inventory investment while meeting service levels.

### Probabilistic Forecasting
Generate forecast distributions (not just point estimates) for better risk assessment and safety stock optimization.

### Supply Chain Network Design
Use optimization models to determine optimal number, location, and size of distribution centers.

### Sales and Operations Planning (S&OP)
Monthly cross-functional process to balance demand and supply, align plans with financials, and make strategic trade-off decisions.

### Supplier Risk Management
Proactive identification and mitigation of supplier financial, operational, and geographic risks through monitoring and contingency planning.

## Troubleshooting

### Forecast Accuracy Issues
- Check data quality (outliers, missing data, stockouts)
- Validate forecast method appropriate for demand pattern
- Incorporate business judgment (promotions, market changes)
- Review forecast parameters and tuning
- Consider ensemble forecasting (combining methods)

### Inventory Imbalances
- Verify demand forecast accuracy and bias
- Review reorder point and safety stock calculations
- Check for lead time variability or supplier issues
- Assess forecast error and demand variability
- Consider ABC segmentation for differentiated policies

### Supplier Performance Problems
- Review scorecard metrics for specific issues
- Conduct root cause analysis (5 Whys, fishbone)
- Engage supplier in improvement plan
- Monitor progress and escalate if needed
- Evaluate alternative suppliers if persistent issues

## Contributing

This plugin is part of the Agentic System Builder framework. Contributions, suggestions, and feedback are welcome.

## License

MIT License - See LICENSE file for details

## Support and Resources

### Documentation
- SCOR Framework: Supply Chain Council
- APICS/ASCM: Supply chain professional association
- ISF: International Institute of Forecasters
- ASQ: American Society for Quality

### Books
- "Supply Chain Management: Strategy, Planning, and Operation" by Chopra & Meindl
- "Forecasting: Principles and Practice" by Hyndman & Athanasopoulos
- "Inventory Management and Production Planning and Scheduling" by Silver, Pyke, Thomas
- "The Six Sigma Handbook" by Pyzdek & Keller

### Online Resources
- APICS certification programs (CPIM, CSCP)
- ISM procurement certifications
- Six Sigma Green Belt / Black Belt training

---

**Version**: 1.0.0
**Last Updated**: 2025-10-24
**Maintained By**: Agentic System Builder Team

For questions, issues, or feature requests, please visit the GitHub repository.
