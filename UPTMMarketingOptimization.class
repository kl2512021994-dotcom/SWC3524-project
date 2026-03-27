import java.util.*;

public class UPTMMarketingOptimization {

    static int[][] costMatrix = {
        {0, 15, 25, 35},
        {15, 0, 30, 28},
        {25, 30, 0, 20},
        {35, 28, 20, 0}
    };

    static String[] locations = {"UPTM", "City B", "City C", "City D"};
 public static String greedyMCOP(int[][] dist) 
{
    int n = dist.length;
    boolean[] visited = new boolean[n];

    int currentCity = 0; // Start at UPTM
    visited[currentCity] = true;

    int totalCost = 0;
    StringBuilder route = new StringBuilder(locations[currentCity]);

    for(int i = 1; i < n; i++)
    {
        int nearestCity = -1;
        int minCost = Integer.MAX_VALUE;

        for(int j = 0; j < n; j++)
        {
            if(!visited[j] && dist[currentCity][j] < minCost)
            {
                minCost = dist[currentCity][j];
                nearestCity = j;
            }
        }

        visited[nearestCity] = true;
        route.append(" -> ").append(locations[nearestCity]);

        totalCost += minCost;
        currentCity = nearestCity;
    }

    totalCost += dist[currentCity][0]; // return to start
    route.append(" -> ").append(locations[0]);

    return "Greedy Route: " + route + " | Total Cost: " + totalCost;
}   
    public static void main(String[] args)
{
    System.out.println(greedyMCOP(costMatrix));
}
}
