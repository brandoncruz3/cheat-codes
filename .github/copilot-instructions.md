# AI Agent Instructions for cheat-codes Repository

This is a curated collection of DevOps cheat sheets, command references, and practical examples organized by technology and domain.

## Repository Structure

### Primary Organization
- `Cheat Sheets/` - Technology-specific command references and guides (tools, services, languages)
- `Examples/` - Working code samples in Javascript, Python, Regex, and Terraform
- Each technology has its own subdirectory with consistent README.md structure

### Hierarchical Categories
The `Cheat Sheets/` directory uses both flat tool-based organization (e.g., `kubectl/`, `docker/`, `terraform/`) and categorical grouping:
- `CICD/` - CI/CD tools (Jenkins, GitHub Actions, ArgoCD, etc.)
- `Languages/` - Programming languages and markup (PHP, Ruby, SQL, YAML, etc.)
- `Cloud/` - Cloud platform specifics
- `Container/` - Container and orchestration tools
- `Network/`, `Security/`, `Automation/` - Domain-specific tools

## Content Patterns

### Standard README Structure
Each technology directory follows this pattern:
- Title with technology name
- Table of contents with anchor links
- Practical command examples with code blocks
- External resource links when relevant
- Organized by use case or component (e.g., kubectl has sections for Pods, Deployments, Secrets)

### Multi-Service Coverage
AWS services are comprehensively covered with both CLI and Python SDK examples:
- `aws-cli/` contains service-specific subdirectories (ec2/, iam/, eks/, etc.)
- `aws-python/` provides boto3 code examples for the same services
- `aws-iam/` contains service-specific IAM policy examples

### Code Examples Format
- Use triple backticks with language specification
- Include complete, runnable commands
- Show expected output when relevant
- Provide context for when to use each command

## Key Integration Points

### Cross-Technology References
- Docker examples reference Kubernetes deployments
- AWS CLI examples complement terraform configurations
- CI/CD tools reference container and deployment strategies

### External Dependencies
- Many examples assume AWS CLI configured with profiles
- Kubernetes examples expect kubectl context setup
- Container examples assume Docker daemon running

## Contribution Guidelines

When adding new content:
1. Create technology-specific subdirectory in appropriate category
2. Use README.md as primary content file
3. Include table of contents with anchor links for sections
4. Provide practical, tested command examples
5. Link to official documentation for comprehensive reference
6. Organize content by common use cases, not alphabetically

### File Naming Conventions
- Use lowercase with hyphens for directory names (`aws-cli`, `github-actions`)
- Technology-specific files use the technology name as filename (`Jenkins.md`, `ArgoCD.md`)
- Keep README.md files for primary content in each directory

## Special Considerations

### Multi-Format Coverage
Some technologies have multiple interface formats:
- CLI tools, SDKs, and configuration files for the same service
- Example: AWS covered via aws-cli/, aws-python/, and terraform/ examples

### Version-Specific Content
- Some tools have version-specific directories (e.g., `helm/` and `helm-2/`)
- Legacy tool versions maintained separately when syntax differs significantly

When working with this codebase, focus on practical utility over comprehensive documentation - users come here for quick reference and copy-paste solutions.