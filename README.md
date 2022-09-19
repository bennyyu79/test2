Bioinformatics Pipeline Documentation Standardization – Laboratory Management Briefing
1.0Purpose
This document outlines standardized approaches and methods that should enhance consistency and reproducibility of bioinformatics pipelines. These methods will help enable the capture of a standard set of metadata and provide transparency to the parameters and tools at each step of an analytical pipeline. This metadata set may vary between groups but ideally should include core information that is always relevant. This will promote reproducible analytics and results as well as provide standardized documentation and capture of bioinformatics analysis. Additionally, this document provides an overview of a few existing standards for analytical metadata capture techniques: Common Workflow Language (CWL), Nextflow, Workflow Description Language (WDL), BioComputeObjects, GeneFlow, Snakemake, and custom log files. Please note that while the aforementioned standards are commonly used, there are several other tools available to accomplish a formal workflow description methodology. We recommend consulting with your bioinformatician or respective analytical personnel to review and evaluate your current metadata capture methods (if present) or consider adoption of the standards outlined in this document. Additionally, we advise directing technical personnel to the “Bioinformatic Pipeline Documentation Standardization Technical Best Practices” document for more guidance and examples.

2.0Scope
This document applies to management personnel responsible for managing Bioinformatics staff tasked with the handling of NGS data, analysis, and any resulting outputs derived through these processes. This document covers capturing bioinformatics workflow and pipeline-specific metadata as well as tools and methods (manual and automated) for the implementation of existing standards and frameworks. Furthermore, this document aims to highlight the benefits and need for analytical metadata standardization.


3.0Related Documents
Title	Document Control Number
Bioinformatic Pipeline Documentation Standardization Technical Best Practices	

4.0Responsibilities 
Position	Responsibility
Management	Review document to understand what standardized metadata capture entails and the benefits gained through implementing it within analytical processes
Review current methods with analytical personnel and consider areas for improvement
Bioinformaticians / Analytical Personnel	Audit current metadata standardization practices if present. Alternatively, seek to adopt one of the standards discussed in this document or an equivalent to achieve the goals highlighted in the following sections
Review examples in “Bioinformatic Pipeline Documentation Standardization Technical Best Practices” for more information

5.0Definitions
Term	Definition
Data Provenance	The documentation of where a piece of data comes from and the processes and methodology by which it was produced.

6.0Introduction
Standardized Metadata Capture for Analytical Frameworks 
The hundreds of millions of reads that come from a gene sequencer represent small, nearly random fragments of the genome that's being sequenced, and there are countless ways in which that data can be transformed to yield insights into microbial surveillance, microbiome dynamics, metagenomics, and many other areas of interest. 
Because there are so many different platforms and so many different scripts and tools to analyze genomic data, there is a great need to standardize the way in which these steps are communicated. The more analysis steps and the more complicated a pipeline, the greater the need for a standardized mechanism of communication. Metadata standards such as CWL, Nextflow, WDL, BioComputeObjects, GeneFlow, Snakemake, and others address this challenge by bringing clarity to an analysis, making it transparent and reproducible. 
Standardized metadata capture advances two major goals: A) understanding the key differences between pipelines (metadata that can affect biologically relevant outcomes) and B) allowing a complete reproduction of an analytical run (sharing and rerunning workflows from start to finish). There are several technical approaches to this process, and based on a laboratory’s needs and available resources, one or more of the approaches described in sections 6–9 below may be the best fit.
7.0Examples of Standardized Metadata Capture for Analytical Frameworks
Common Workflow Language
The Common Workflow Language (CWL) is an open standard for describing analysis workflows and tools in a way that makes them portable and scalable across a variety of software and hardware environments, from workstations to cluster, cloud, and high-performance computing (HPC) environments. CWL is designed to meet the needs of data-intensive sciences, such as bioinformatics, medical imaging, and machine learning.
CWL is developed by a multi-vendor working group consisting of organizations and individuals aiming to enable scientists to share data analysis workflows. The CWL project is maintained on GitHub and follows the Open-Stand.org principles for collaborative open standards development. Legally CWL is a member project of Software Freedom Conservancy and is formally managed by the elected CWL leadership team. However, everyday project decisions are made by the CWL community, which is open to all participants.
CWL definitions are comparatively simple, and responsibilities are split into three components: data inputs (“Jobs” in CWL terms), software inputs (“Tools”), and “Workflows”. CWL documents are in standard text serialization file formats, Javascript Object Notation (JSON) and YAML.
Nextflow
Nextflow enables scalable and reproducible scientific workflows through software containerization. It allows the adaptation of pipelines written in many common scripting languages. Its fluent Domain Specific Language (DSL) aims to simplify the implementation and the deployment of complex parallel and reactive workflows on clouds and clusters.
It is designed around the idea that the Linux platform is central to the domain of data science. Linux provides many simple but powerful command-line and scripting tools that, when chained together, facilitate complex data manipulations. Nextflow extends this principle, adding the ability to define complex program interactions and a high-level parallel computational environment based on the dataflow programming model.
Workflow Description Language
The Workflow Description Language (WDL) is a standard for description and characterization of data processing workflows with a human-readable and writeable syntax. WDL allows users to describe complex analytical tasks, chain them together into workflows, and parallelize their execution. The language makes common patterns simple to express, while also admitting uncommon or complicated behavior; and it strives to achieve portability not only across execution platforms, but also across different types of users. 
WDL was originally developed for genome analysis pipelines by the Broad Institute. Over time, it was transitioned into OpenWDL to allow for a more community driven focus. The OpenWDL community has thus been formed to steward the WDL language specification and advocate its adoption.
BioCompute Object
A BioCompute Object (BCO) is an instance of the BioCompute standard and is a computational record of a bioinformatics pipeline. A BCO is not an analysis but rather is a record of which analyses were executed and in exactly which ways. In this way, a BCO acts as an interface for existing standards. A BCO contains all the necessary information to repeat an entire pipeline from FASTQ to result and includes additional metadata to identify provenance (point of origin) and usage. This standard has been implemented and tested with platforms including HIVE, Galaxy, Seven Bridges, DNA Nexus and others.
A BCO is a set of key:value pairs (meaning that raw files can be read without any knowledge of programming) written to a JSON file. Information within the BCO is organized into "domains." The domains within a BCO record are as follows: Provenance, Usability, Extension, Description, Execution, Input/Output, and Parametric. For more information on the domains, please see the Bioinformatic Pipeline Documentation Standardization Technical Best Practices Document.
GeneFlow
GeneFlow is a workflow framework that consists of a definition language (containing standard metadata) and a workflow engine. The former is the component of most relevance to this document, as it serves a similar role to a BCO in defining a set of data to be captured from a bioinformatics workflow. Geneflow supports tools and technologies (i.e., web interfaces, command line tools, community repositories, and standards). It was developed for the Centers for Disease Control and Prevention by the Scientific Computing and Bioinformatics Support (SCBS) team to assist with pipeline standardization and ease of use. 
Geneflow captures various information in YAML format and is designed to be human-readable, thus allowing team members to easily understand the information being captured and represented therein. This information includes Metadata (general workflow information), Inputs (files or folder inputs required by the workflow), Parameters (other data besides files or folders, required by the workflow), and Steps (a list of analytical tasks to be performed by the workflow)
Snakemake
Snakemake is a workflow framework that aims to provide a human-readable, Python-based, workflow-definition language that is both powerful and scalable (works without modification from a single-core workstation to computing clusters). It is the first system to support the use of automatically inferred, multiply named wildcards (or variables) within input and output filenames (e.g., an asterisk (*), which can be interpreted as a number of characters or an empty string). Additionally, Snakemake interoperates with any installed tool or available web services with well-defined input and output file formats.
Workflows are defined in “Snakefiles” through a domain-specific language similar to standard Python syntax. These files are made up of rules that describe how output files are generated from the input file(s) in the associated pipeline. Each rule definition specifies a name, any number of input and output files, and either a shell command or python code that creates the specified output from given inputs. Directed acyclic graphs or DAGs can then be used to represent a plan of rule executions.
Custom Log File
While established standards might be applicable to some, it is important to recognize that there is a wide range in use cases in which bioinformaticians may opt to produce their own custom log files to document analytical workflows. It is recommended that Part 2 of the Bioinformatics Pipeline Documentation Standardization Technical Best Practices Document be utilized to inform the selection of metadata and design of these custom logs, regardless of file format or the data structure selected.
8.0Benefits and Value Added
Proper implementation of one or more of the aforementioned methods will provide a number of benefits and value—making bioinformatics workflows more shareable, transparent, and reproducible. Additionally, such implementations would promote best practices and serve to reduce the burden placed on bioinformaticians and research teams resulting from a lack of sufficient documentation. 
As mentioned above, these benefits would help teams achieve the two primary goals: 
A) Providing a sample-to-run mapping document highlighting specific metadata that’s significant in affecting a run output, which allows for the identification of key differences and discrepancies from resulting analysis so that they can be resolved.
B) Capturing run information in a transparent text file (i.e. JSON or YAML), which allows for complete reproduction of an analysis, starting with FASTQ files and continuing all the way to the final output from a pipeline.

9.0References
9.1BioComputeObjects. (2018). Retrieved October 2, 2019, from https://biocomputeobject.org/about.html.
9.2Köster, J. & Rahmann, S. 2012. Snakemake—a scalable bioinformatics workflow engine, Bioinformatics, 28(19): 2520–2.https://doi.org/10.1093/bioinformatics/bts480 
9.3Nextflow. (n.d.). Retrieved June 22, 2020, from https://www.nextflow.io/ 
9.4OAMD Scientific Computing and Bioinformatics Support Team. (2019, July). GeneFlow: A Framework for Building, Running, and Sharing Bioinformatics Workflows.
9.5OpenWDL. (n.d.). Retrieved June 22, 2020, from https://openwdl.org/#  
9.6Peter Amstutz, Michael R. Crusoe, Nebojša Tijanić (editors), Brad Chapman, John Chilton, Michael Heuer, Andrey Kartashov, Dan Leehr, Hervé Ménager, Maya Nedeljkovich, Matt Scales, Stian Soiland-Reyes, Luka Stojanovic (2016): Common Workflow Language, v1.0. Specification, Common Workflow Language working group. https://w3id.org/cwl/v1.0/, doi:10.6084/m9.figshare.3115156.v2 
9.7Prins, P. (2019, January 21). Creating a reproducible workflow with CWL. Retrieved June 22, 2020, from https://hpc.guix.info/blog/2019/01/creating-a-reproducible-workflow-with-cwl/ 
10.0Revision History
Rev #	DCR #	Change Summary	Date
			
