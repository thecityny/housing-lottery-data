# Housing Lottery Methodology

THE CITY used two datasets to calculate the competition for Housing New York apartments at different income levels: a [spreadsheet](housing-lotteries.csv) of 426 affordable housing lotteries that took place from 2014 to 2019, and a [list](lottery-applications.csv) of more than 20 million lottery applications provided by the Department of Housing Preservation and Development.

The list of lotteries contained 1,888 groups of housing units of different sizes set aside for applicants at a range of income levels. Under city and federal programs, apartments are targeted to households based on how their incomes compare to the New York City area’s median as [determined annually](https://www.huduser.gov/portal/datasets/il.html) by the U.S. Department of Housing and Urban Development.

We assigned a percentage of area median income to each group of units based on the income limits for each group and the year the lottery opened.

We determined how many applicants were potentially eligible for each unit by comparing all the applications in a given lottery to the available units, finding the income limits for the applicant’s household size and filtering out the units that didn’t match the applicant’s income. About two- thirds of applicants didn’t qualify for any units based on income and were excluded from our analysis.

We grouped units into the [income limit bands](https://www1.nyc.gov/site/hpd/services-and-information/area-median-income.page) used by New York City government housing agencies (0-30% AMI, 31-50% AMI, etc.), and counted the number of unique applicants qualifying for units in each band. We divided the result by the available units to arrive at the applicant-to-unit ratio.

## Assigning AMI percentages

To group units into the income bands used by city housing agencies, we had to know the percentage of median income used to set the income limits on each apartment. The data provided by HPD did not include the percentage of AMI, but it did list each household size eligible for a unit and the associated maximum income limit.

We calculated the percentage of AMI by dividing the maximum income limit for the smallest household size for each unit by the HUD definition for “very low income” (VLI) for that household size and year. VLI is the figure used by HPD to set most income limits and represents 50% of median income, adjusted to meet statutory requirements. For example, the VLI dollar figure provided by HUD for a New York City family of three in 2020 is $51,200. The income maximum for a family of three for a 60% AMI unit is 60% of $51,200 multiplied by two, or $61,440.

In most cases we used the VLI figure for the year the housing lottery opened, but in cases when the resulting percentage was not an integer, we used the VLI figure for the year before the lottery opened, assuming income limits were set in the prior year. For example, this corrected percentages that would have been 54.9% of AMI using the VLI figure for the year the lottery opened to 60% using the VLI figure from the year before.

Some lotteries listed AMI percentages on their advertisements. For every lottery where this was the case, we checked the percentages we calculated against all lottery advertisements and confirmed that our assignments were correct.

## Community preference

To calculate the ratio of applications to units for people with and without community preference, we used data from [an analysis](http://www.antibiaslaw.com/sites/default/files/Bevdec1.pdf) conducted as part of a civil rights lawsuit against the city, which placed the share of eligible applicants to housing lotteries who qualified for community preference at 5.5%.

We used 5.5% of all eligible applicants in our data to estimate the population qualifying for community preference. Additionally, we used housing lottery advertisements to identify 9,934 community preference units and 11,448 non-community-preference units in our data.

The ratio for “insiders” was our estimate of applicants qualifying for community preference divided by the number of community preference units available based on lottery advertisements.

Assuming all community preference set-asides would be filled, we subtracted the number of community preference units from the total number of eligible applicants and divided by the number of non-community preference units for the ratio of “outsider” applications to available units.

## Caveats

Although we checked for eligibility based on income, the available data did not allow us to weigh additional eligibility factors, such as age, which vary by lottery. We were also not able to account for set-asides of some apartments for special groups of applicants, such as people with disabilities, beyond our estimates of the effects of community preference.

Applicants are only uniquely identified at the lottery level, so an individual who applies to more than one lottery is counted more than once. Lotteries also often contain a mix of income limits, so an applicant who qualifies for units that fall into two different income bands in the same lottery is counted in each calculation. For example, the [810 River](https://a806-housingconnect.nyc.gov/nyclottery/AdvertisementPdf/379.pdf) lottery had studio apartments available at 90% AMI (moderate income) and 130% AMI (middle income). The income limits for a household of one were $37,852-$60,120 for the 90% unit and $43,440 - $86,840 for the 130% unit. An applicant making $50,000 would have qualified for both and was counted in both income bands.

The resulting ratios represent the competition for apartments, not necessarily the odds of successfully getting an apartment in a particular income band. Many other factors play into who ultimately gets a unit. Some applicants who submit paperwork end up not meeting the income requirements, and others who successfully qualify decide not to take the apartment. The chances of winning an apartment for someone meeting all eligibility requirements are likely higher, particularly those matching a set-aside category.
