# Chapter 1
In a famous 1996 paper, 11 David Wolpert demonstrated that if you
make absolutely no assumption about the data, then there is no reason
to prefer one model over any other. This is called the **No Free Lunch
(NFL)** theorem.

-----
# Chapter 2
A sequence of data processing components is called a _data pipeline_.
Pipelines are very common in Machine Learning systems, since there is a
lot of data to manipulate and many data transformations to apply.
Components typically run asynchronously. Each component pulls in a
large amount of data, processes it, and spits out the result in another data
store. Then, some time later, the next component in the pipeline pulls this
data and spits out its own output. Each component is fairly self-contained:
the interface between components is simply the data store. This makes the
system simple to grasp (with the help of a data flow graph), and different
teams can focus on different components. Moreover, if a component
breaks down, the downstream components can often continue to run
normally (at least for a while) by just using the last output from the
broken component. This makes the architecture quite robust.
On the other hand, a broken component can go unnoticed for some time if
proper monitoring is not implemented. The data gets stale and the overall
system’s performance drops.

