# Training Mapping Project

A document processing pipeline that transforms training guide materials into organized, searchable markdown files.

## Project Overview

This project scans a 2GB+ training document library and produces:
- **Structured markdown files** organized by group, organization, and topic
- **Cross-reference indexes** for easy navigation
- **Metadata extraction** for searchability

## Directory Structure

```
Training Mapping/
├── config/                 # Configuration files
│   ├── scan-config.json   # Source paths and scan settings
│   └── taxonomy.json      # Group/Org/Topic classification rules
├── output/
│   ├── by-group/          # Markdown files organized by training group
│   ├── by-org/            # Markdown files organized by organization
│   ├── by-topic/          # Markdown files organized by topic/subject
│   └── index/             # Master indexes and cross-references
├── scripts/               # Processing scripts (if needed)
├── logs/                  # Scan and processing logs
├── source-analysis/       # Analysis reports of source structure
└── README.md
```

## Workflow

1. **Source Analysis** - Scan source folder structure to understand organization
2. **Taxonomy Definition** - Define groups, orgs, and topic classifications
3. **Document Processing** - Walk all documents and extract content
4. **Markdown Generation** - Create organized markdown files
5. **Index Building** - Generate navigation indexes

## Source Data

- **Location**: [To be configured]
- **Size**: ~2GB
- **Types**: [To be discovered during scan]

## Status

- [ ] Project structure created
- [ ] Source folder scanned
- [ ] Taxonomy defined
- [ ] Processing pipeline ready
- [ ] Document conversion complete
- [ ] Indexes generated
