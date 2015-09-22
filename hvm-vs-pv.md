AWS Xen Full virtualization (HVM) vs Xen Paravirtualization (PV)

Tags: aws, virtualization, hvm, pv

# Intro

Amazon Web sergices EC2 offeres two ways of virtualization: Xen HVM and Xen PV.

1. Which one is faster?
2. which one gives less trouble?
3. Is ther any cost difference?

## PV
  * The guest VM needs some modifications on its kernel, so it can work with the host.

    * No problem since PV AMIs in Amazon have such modifications.
    * It may be a problem with other op. systems (BSD, maybe Windows).
  
  * Every access to the hardware is handled directly between guest VM and the hardware, w/o intervention of the host OS.

## HVM

  * Guest VM is a normal kernel, w/o modifications.
    * Requires some newer hardware [3].
  * Accesses to hardware trigger interruptions that must be handled by host OS.
    * This is supposed to introduce performance penalties, I'd say, specially in I/O: disk or network.
    * It is not clear if there are actually such penalties. See [1].
  

# Conclussions

Given the results in [1], it seems HVM offers **not great performance penalty** over PV. Nonetheless, I think **benchmarking was not very I/O oriented**, but more processor/memory crunching.

Will  it give better results for I/O related purposes (e.g. ElasticSearch server, PostgresSQL server, etc.)?

E.g. in *Timed Linux Kernel Compilation v3.1* test [1] HVM makes better than PV. In *Apache Benchmark v2.4.7 Static Web Page Serving* it seems HVM also makes better than PV.

# Refs:

1. [Phoronix: Ubuntu 14.04 On Amazon EC2: Xen PV vs. HVM](http://www.phoronix.com/scan.php?page=article&item=amazon_ec2_pvhvm&num=1)

2. [LinxQuestions.org: HVM vs PV (Xen Full virtualization (HVM) Xen Paravirtualization (PV))](http://www.linuxquestions.org/questions/linux-virtualization-and-cloud-90/hvm-vs-pv-xen-full-virtualization-hvm-xen-paravirtualization-pv-872427/)

3. [What is the difference between PV and HVM virtualization types in ec2?](http://serverfault.com/questions/637102/what-is-the-difference-between-pv-and-hvm-virtualization-types-in-ec2)
