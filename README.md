# Assigment2-vishnumolakala

## subhash nethra vishnumolakala
### my favourite place is my village which is Jaddangi <br>

my village is a place that I perfer most for holiday the people are very friendly its a famous place for nature lovers ofcourse its place away from **pollution** and **noise** from major cities .The cool breeze at night and warm but pleasant breeze in the day.

-----

# Direction from maryvillie to Jaddangi 
1. The  Journey start from  kansas city airport  
2. From   kansas to chicago has a direct flight  
3. after reaching chicago to we have connecting flight to dallas
      1. From dallas airport to Delhi airport have direct flight 
      2. After reaching delhi airport we have a local flight to reachout to  rajahmundry airport 
      3. Need to travel exactly one hour from airport we can reachout to our hometown 

 * books 
 * clothes 
 * sweets 

 [AboutMe link](AboutMe.md)   


 -----

## Mostly popular food/drinks
below table illustrates some drinks and food item which i recommend  to try.


| food / drinks   | locations around | prices of the items |
| --------------- | ---------------  | ---------------     |
| chicken nuggets | ohio, USA        | 10 for each piece   |
| veg briyani spl | dallas, USA      | 15 for each packet  | 
| chicken briyani | new york city,USA| 25 for each packet  | 
|  sprit          | chicago,USA      | 6  for each bottle  |
| red bull        | los angles       | 13 for each tin     | 
---
# pithy quotes 
 “I have only made this letter longer because I have not had the time to make it shorter."
― *Blaise Pascal, The Provincial Letters*
 “Mathematicians deal with large numbers sometimes, but never in their income.”
― *Isaac Asimov, Prelude to Foundation*
 

 ---
 # code Fencing
 ----- 
 int n;
vector<vector<int>> adj;
vector<char> color;
vector<int> parent;
int cycle_start, cycle_end;

bool dfs(int v) {
    color[v] = 1;
    for (int u : adj[v]) {
        if (color[u] == 0) {
            parent[u] = v;
            if (dfs(u))
                return true;
        } else if (color[u] == 1) {
            cycle_end = v;
            cycle_start = u;
            return true;
        }
    }
    color[v] = 2;
    return false;
}

void find_cycle() {
    color.assign(n, 0);
    parent.assign(n, -1);
    cycle_start = -1;

    for (int v = 0; v < n; v++) {
        if (color[v] == 0 && dfs(v))
            break;
    }

    if (cycle_start == -1) {
        cout << "Acyclic" << endl;
    } else {
        vector<int> cycle;
        cycle.push_back(cycle_start);
        for (int v = cycle_end; v != cycle_start; v = parent[v])
            cycle.push_back(v);
        cycle.push_back(cycle_start);
        reverse(cycle.begin(), cycle.end());

        cout << "Cycle found: ";
        for (int v : cycle)
            cout << v << " ";
        cout << endl;
    }
}

----
https://cp-algorithms.com/graph/finding-cycle.html



