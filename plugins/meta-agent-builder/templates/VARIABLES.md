# Template Variables Quick Reference

This document provides a quick lookup for all template variables used in the agentic system builder templates.

## Agent Template Variables

| Variable | Type | Example | Description |
|----------|------|---------|-------------|
| `{{AGENT_NAME}}` | identifier | `inventory-manager` | Hyphen-case agent identifier |
| `{{DESCRIPTION}}` | text | `Manage inventory with stock tracking` | Brief description < 200 chars |
| `{{MODEL}}` | enum | `haiku`, `sonnet`, `opus` | AI model to use |
| `{{USE_WHEN_CLAUSE}}` | text | `for inventory management or stock analysis` | Proactive activation criteria |
| `{{AGENT_ROLE}}` | text | `an expert inventory management specialist` | Full agent role/title |
| `{{SPECIALIZATION}}` | text | `stock optimization and supply chain automation` | Primary expertise area |
| `{{PURPOSE_STATEMENT}}` | paragraph | `Expert in managing inventory systems...` | Detailed purpose (1-2 paragraphs) |
| `{{CAPABILITY_CATEGORY_1}}` | title | `Inventory Tracking & Monitoring` | First capability category |
| `{{CAPABILITY_1_ITEMS}}` | list | `- Real-time stock level tracking\n- Low stock alerts` | Bulleted capabilities |
| `{{CAPABILITY_CATEGORY_2}}` | title | `Forecasting & Analysis` | Second capability category |
| `{{CAPABILITY_2_ITEMS}}` | list | `- Demand forecasting\n- Trend analysis` | Bulleted capabilities |
| `{{CAPABILITY_CATEGORY_3}}` | title | `Automation & Optimization` | Third capability category |
| `{{CAPABILITY_3_ITEMS}}` | list | `- Automated reordering\n- Stock optimization` | Bulleted capabilities |
| `{{BEHAVIORAL_TRAITS}}` | list | `- Proactive in identifying stock issues\n- Data-driven` | Behavioral characteristics |
| `{{KNOWLEDGE_BASE_ITEMS}}` | list | `- Inventory management best practices\n- Supply chain` | Knowledge areas |
| `{{STEP_1_TITLE}}` | title | `Assess Current State` | First response step title |
| `{{STEP_1_DESCRIPTION}}` | text | `Analyze current inventory levels and trends` | Step description |
| `{{STEP_2_TITLE}}` | title | `Analyze Patterns` | Second response step title |
| `{{STEP_2_DESCRIPTION}}` | text | `Identify demand patterns and seasonality` | Step description |
| `{{STEP_3_TITLE}}` | title | `Generate Recommendations` | Third response step title |
| `{{STEP_3_DESCRIPTION}}` | text | `Provide actionable stock recommendations` | Step description |
| `{{STEP_4_TITLE}}` | title | `Implement Automation` | Fourth response step title |
| `{{STEP_4_DESCRIPTION}}` | text | `Set up automated reorder triggers` | Step description |
| `{{STEP_5_TITLE}}` | title | `Monitor & Optimize` | Fifth response step title |
| `{{STEP_5_DESCRIPTION}}` | text | `Track results and refine approach` | Step description |
| `{{EXAMPLE_INTERACTIONS}}` | list | `- "Analyze Q4 stock levels"\n- "Set up reorder automation"` | Usage examples |

## Skill Template Variables

| Variable | Type | Example | Description |
|----------|------|---------|-------------|
| `{{SKILL_NAME}}` | identifier | `inventory-optimization` | Hyphen-case skill identifier |
| `{{DESCRIPTION}}` | text | `Optimize inventory levels with EOQ. Use when...` | Description < 1024 chars with "Use when" |
| `{{WHEN_TO_USE_CLAUSE}}` | text | `managing stock levels or implementing reorder automation` | Activation scenarios |
| `{{SKILL_TITLE}}` | title | `Inventory Optimization Patterns` | Display title |
| `{{SKILL_OVERVIEW}}` | paragraph | `Master inventory management with advanced...` | 1-2 paragraph overview |
| `{{WHEN_TO_USE_LIST}}` | list | `- Managing stock levels\n- Implementing reorder` | Bulleted use cases |
| `{{CONCEPT_1_TITLE}}` | title | `Economic Order Quantity (EOQ)` | First core concept |
| `{{CONCEPT_1_DESCRIPTION}}` | paragraph | `EOQ is the optimal order quantity...` | Concept explanation |
| `{{CONCEPT_2_TITLE}}` | title | `Reorder Point Calculation` | Second core concept |
| `{{CONCEPT_2_DESCRIPTION}}` | paragraph | `The reorder point determines when...` | Concept explanation |
| `{{CONCEPT_3_TITLE}}` | title | `Safety Stock Management` | Third core concept |
| `{{CONCEPT_3_DESCRIPTION}}` | paragraph | `Safety stock provides buffer against...` | Concept explanation |
| `{{QUICK_START_CODE_EXAMPLE}}` | code | `python\neoq = sqrt((2 * demand * order_cost)...)` | Minimal working example |
| `{{MAIN_SECTION_TITLE}}` | title | `Implementation Patterns` | Main section header |
| `{{PATTERN_1_TITLE}}` | title | `EOQ with Variable Demand` | First pattern name |
| `{{PATTERN_1_DESCRIPTION}}` | paragraph | `Handle fluctuating demand with adaptive EOQ...` | Pattern explanation |
| `{{PATTERN_1_CODE}}` | code | Full code example | Pattern implementation |
| `{{PATTERN_2_TITLE}}` | title | `Automated Reorder Triggering` | Second pattern name |
| `{{PATTERN_2_DESCRIPTION}}` | paragraph | `Automate reorders based on thresholds...` | Pattern explanation |
| `{{PATTERN_2_CODE}}` | code | Full code example | Pattern implementation |
| `{{PATTERN_3_TITLE}}` | title | `Multi-location Inventory Balancing` | Third pattern name |
| `{{PATTERN_3_DESCRIPTION}}` | paragraph | `Balance stock across multiple warehouses...` | Pattern explanation |
| `{{PATTERN_3_CODE}}` | code | Full code example | Pattern implementation |
| `{{CODE_LANGUAGE}}` | enum | `python`, `javascript`, `sql`, etc. | Language for syntax highlighting |
| `{{ADVANCED_SECTION_TITLE}}` | title | `Advanced Techniques` | Advanced section header |
| `{{ADVANCED_CONTENT}}` | markdown | Full content with subsections | Advanced material |
| `{{RESOURCES_LIST}}` | list | `- **references/eoq.md**: EOQ formulas` | Reference materials |
| `{{BEST_PRACTICES_LIST}}` | list | `1. **Monitor Lead Times**: Track supplier performance` | Best practices numbered list |
| `{{COMMON_PITFALLS_LIST}}` | list | `- **Ignoring Demand Variance**: Fixed EOQ can fail` | Pitfalls bulleted list |

## Command Template Variables

| Variable | Type | Example | Description |
|----------|------|---------|-------------|
| `{{COMMAND_DESCRIPTION}}` | text | `Generate inventory reorder recommendations` | What the command does |
| `{{ARGUMENT_HINT}}` | text | `[product-category] [forecast-period]` | Parameter hints |
| `{{VERSION}}` | semver | `1.0.0` | Semantic version |
| `{{TAGS}}` | list | `inventory, forecasting, automation` | Comma-separated tags |
| `{{TOOL_ACCESS}}` | list | `Read, Write, Bash, Grep` | Required tools |
| `{{MODEL}}` | enum | `sonnet`, `haiku` | AI model to use |
| `{{COMMAND_TITLE}}` | title | `Inventory Reorder Automation` | Display title |
| `{{COMMAND_OVERVIEW}}` | paragraph | `Generate data-driven reorder recommendations...` | Overview paragraph |
| `{{CONTEXT_DESCRIPTION}}` | paragraph | `This command analyzes historical sales data...` | Context explanation |
| `{{PHASE_1_TITLE}}` | title | `Data Collection & Analysis` | First phase header |
| `{{PHASE_1_DESCRIPTION}}` | text | `Gather historical sales and inventory data` | Phase description |
| `{{PHASE_1_CONTENT}}` | markdown | Full phase content with instructions | Implementation details |
| `{{PHASE_2_TITLE}}` | title | `Demand Forecasting` | Second phase header |
| `{{PHASE_2_DESCRIPTION}}` | text | `Generate demand forecasts using time series` | Phase description |
| `{{PHASE_2_CONTENT}}` | markdown | Full phase content | Implementation details |
| `{{PHASE_3_TITLE}}` | title | `Recommendation Generation` | Third phase header |
| `{{PHASE_3_DESCRIPTION}}` | text | `Calculate optimal reorder quantities` | Phase description |
| `{{PHASE_3_CONTENT}}` | markdown | Full phase content | Implementation details |
| `{{OUTPUT_FORMAT_ITEMS}}` | list | `1. **Reorder Report**: Products needing reorder` | Expected outputs |
| `{{SUCCESS_CRITERIA_ITEMS}}` | list | `- Forecast accuracy > 80%\n- Recommendations generated` | Success metrics |
| `{{RELATED_PLUGINS}}` | list | `- **supply-chain-ops**: Advanced optimization` | Related plugin references |

**Note:** Commands always use `$ARGUMENTS` as the placeholder for user input in the Requirements section.

## Plugin Manifest Variables

| Variable | Type | Example | Description |
|----------|------|---------|-------------|
| `{{PLUGIN_NAME}}` | identifier | `inventory-management` | Hyphen-case plugin identifier |
| `{{PLUGIN_DESCRIPTION}}` | text | `Inventory tracking, optimization, and automation` | Plugin purpose |
| `{{VERSION}}` | semver | `1.0.0` | Semantic version |
| `{{AUTHOR_NAME}}` | text | `John Smith` | Author full name |
| `{{AUTHOR_URL}}` | url | `https://github.com/username` | Author URL or profile |
| `{{HOMEPAGE_URL}}` | url | `https://github.com/username/agents` | Plugin homepage |
| `{{REPOSITORY_URL}}` | url | `https://github.com/username/agents` | Git repository URL |
| `{{LICENSE}}` | text | `MIT` | License type |
| `{{KEYWORDS}}` | list | `"inventory", "stock", "forecasting"` | Comma-separated quoted keywords |
| `{{CATEGORY}}` | enum | `operations`, `business`, `workflows`, etc. | Plugin category |
| `{{COMMANDS_ARRAY}}` | json | `"./commands/reorder.md", "./commands/forecast.md"` | Comma-separated command paths |
| `{{AGENTS_ARRAY}}` | json | `"./agents/inventory-manager.md", "./agents/optimizer.md"` | Comma-separated agent paths |
| `{{SKILLS_ARRAY}}` | json | `"./skills/inventory-opt", "./skills/forecasting"` | Comma-separated skill paths |

## Variable Type Definitions

### identifier
- Format: `hyphen-case`
- Pattern: `^[a-z][a-z0-9-]*$`
- Example: `inventory-manager`

### text
- Short string, typically < 200 chars
- No formatting, plain text
- Example: `Manage inventory with automated reordering`

### paragraph
- Multi-sentence text, 1-2 paragraphs
- Can span multiple lines
- Example: `Expert in managing inventory systems with real-time tracking...`

### title
- Title case string
- Used for section headers
- Example: `Inventory Tracking & Monitoring`

### list
- Markdown formatted list (bulleted or numbered)
- Each item on new line
- Example: `- Item one\n- Item two`

### markdown
- Full markdown content
- Can include headers, lists, code blocks
- May span many lines

### code
- Code block content
- Language specified separately
- Example: `def calculate_eoq():\n    return sqrt(...)`

### enum
- One of a fixed set of values
- Examples: `haiku|sonnet|opus`, `python|javascript|sql`

### semver
- Semantic version format
- Pattern: `^\d+\.\d+\.\d+$`
- Example: `1.0.0`

### url
- Valid URL
- Must start with `http://` or `https://`
- Example: `https://github.com/username`

### json
- Valid JSON syntax
- For arrays: comma-separated quoted strings
- Example: `"item1", "item2", "item3"`

## Replacement Examples

### Simple String Replacement (Python)
```python
template = template.replace('{{AGENT_NAME}}', 'inventory-manager')
```

### Dictionary-Based Replacement (Python)
```python
replacements = {
    'AGENT_NAME': 'inventory-manager',
    'DESCRIPTION': 'Manage inventory with stock tracking',
    'MODEL': 'haiku'
}

for key, value in replacements.items():
    template = template.replace(f'{{{{{key}}}}}', value)
```

### Regex-Based Replacement (Python)
```python
import re

def fill_template(template, replacements):
    def replace(match):
        key = match.group(1)
        return replacements.get(key, match.group(0))

    return re.sub(r'\{\{([A-Z_0-9]+)\}\}', replace, template)
```

## Variable Naming Rules

1. **All uppercase** with underscores: `AGENT_NAME`, `CAPABILITY_CATEGORY_1`
2. **Descriptive names** that indicate content: `STEP_1_TITLE` not `VAR_1`
3. **Numbered variants** for repeated patterns: `PATTERN_1_CODE`, `PATTERN_2_CODE`
4. **Consistent suffixes**:
   - `_TITLE` for section headers
   - `_DESCRIPTION` for explanations
   - `_ITEMS` for lists
   - `_CONTENT` for full sections
   - `_CODE` for code blocks

## Multi-line Content Formatting

When filling multi-line variables:

**Lists:**
```python
CAPABILITY_1_ITEMS = """- Real-time stock level tracking
- Low stock alerts and notifications
- Stock movement history
- Multi-location inventory visibility"""
```

**Paragraphs:**
```python
PURPOSE_STATEMENT = """Expert in managing inventory systems with real-time tracking,
automated reordering, and demand forecasting. Optimizes stock levels to reduce carrying
costs while maintaining service levels."""
```

**Code Blocks:**
```python
PATTERN_1_CODE = """def calculate_eoq(demand, order_cost, holding_cost):
    return math.sqrt((2 * demand * order_cost) / holding_cost)

eoq = calculate_eoq(annual_demand=10000, order_cost=50, holding_cost=2)
print(f"Optimal order quantity: {eoq}")"""
```

## Optional Variables

Some templates support optional variables. If not provided:
- Keep the placeholder (for manual editing)
- Remove the section entirely (for clean output)
- Use default values

**Example:** If `{{BEHAVIORAL_TRAITS}}` is optional, either:
1. Fill with traits: `- Proactive\n- Data-driven`
2. Remove the entire "Behavioral Traits" section
3. Leave as `{{BEHAVIORAL_TRAITS}}` for manual editing

## Validation

Before using filled template:

1. **Check for remaining placeholders:** `{{.*}}`
2. **Validate syntax:** YAML frontmatter, JSON structure
3. **Verify required fields:** Name, description, model
4. **Test file structure:** Can it be parsed?
5. **Check file paths:** Do referenced files exist?

## Additional Resources

- **README.md** - Comprehensive template usage guide
- **agent-template.md** - Agent template with all placeholders
- **skill-template.md** - Skill template with all placeholders
- **command-template.md** - Command template with all placeholders
- **plugin-manifest-template.json** - Plugin manifest with all placeholders
