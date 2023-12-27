#include <bits/stdc++.h><br>
#include <iomanip><br>
#include <string><br>
#include <algorithm><br>
using namespace std;<br>

struct Element {<br>
    int AtomicNo;<br>
    string name, symbol;<br>
    float mass;<br>
    string type;<br>
};<br>

void display(Element arr[], int size) {<br>
    cout << "               MODERN PERIODIC TABLE" << endl;<br>
    cout << "----------------------------------------------------------------" << endl;<br>
    cout << "| No | Element name | Symbol | Atomic Mass | Type              |" << endl;<br>
    cout << "----------------------------------------------------------------" << endl;<br>
    for (int i = 0; i < size; i++) {<br>
        cout << "|" << setw(3) << arr[i].AtomicNo << " |";<br>
        cout << setw(13) << arr[i].name << " |";<br>
        cout << setw(7) << arr[i].symbol << " |";<br>
        cout << setw(12) << arr[i].mass << " |";<br>
        cout << setw(18) << arr[i].type << " |" << endl;<br>
    }<br>
    cout << "----------------------------------------------------------------" << endl;<br>
}<br>

int search(Element arr[], int size, const string& query) {<br>
    string Q = query;<br>
    transform(Q.begin(), Q.end(), Q.begin(), ::toupper);<br>

    for (int i = 0; i < size; i++) {
        string e_name = arr[i].name;
        string e_symbol = arr[i].symbol; 
        string e_type = arr[i].type; 
        transform(e_name.begin(), e_name.end(), e_name.begin(), ::toupper); 
        transform(e_symbol.begin(), e_symbol.end(), e_symbol.begin(), ::toupper); 
        transform(e_type.begin(), e_type.end(), e_type.begin(), ::toupper); 

        if (e_name == Q || e_symbol == Q) { 
            return i;  
        } 
    } 
    return -1;  
} 

int main() {<br>
    const int size = 118; <br>
    Element table[size] = {<br>
        {1, "Hydrogen", "H", 1.0079, "Non-metal"},<br>
        {2, "Helium", "He", 4.0026, "Noble Gase"},<br>
        {3, "Lithium", "Li", 6.941, "Alkali Metal"},<br>
        {4, "Beryllium", "Be", 9.0122, "Alkaline Earth"},<br>
        {5, "Boron", "B", 10.811, "Semi-metal"},<br>
        {6, "Carbon", "C", 12.0107, "Non-metal"},<br>
        {7, "Nitrogen", "N", 14.0067, "Non-metal"},<br>
        {8, "Oxygen", "O", 15.9994, "Non-metal"},<br>
        {9, "Fluorine", "F", 18.9984, "Halogen"},<br>
        {10, "Neon", "Ne", 20.1797, "Noble Gase"},<br>
        {11, "Sodium", "Na", 22.9898, "Alkali Metal"},<br>
        {12, "Magnesium", "Mg", 24.305, "Alkaline Earth"},<br>
        {13, "Aluminum", "Al", 26.9815, "Basic Metal"},<br>
        {14, "Silicon", "Si", 28.085, "Semi-metal"},<br>
        {15, "Phosphorus", "P", 30.9738, "Non-metal"},<br>
        {16, "Sulfur", "S", 32.06, "Non-metal"},<br>
        {17, "Chlorine", "Cl", 35.45, "Halogen"},<br>
        {18, "Argon", "Ar", 39.948, "Noble Gase"},<br>
        {19, "Potassium", "K", 39.0983, "Alkali Metal"},<br>
        {20, "Calcium", "Ca", 40.078, "Alkaline Earth"},<br>
        {21, "Scandium", "Sc", 44.9559, "Transition Metal"},<br>
        {22, "Titanium", "Ti", 47.867, "Transition Metal"},<br>
        {23, "Vanadium", "V", 50.9415, "Transition Metal"},<br>
        {24, "Chromium", "Cr", 51.9961, "Transition Metal"},<br>
        {25, "Manganese", "Mn", 54.938, "Transition Metal"},<br>
        {26, "Iron", "Fe", 55.845, "Transition Metal"},<br>
        {27, "Cobalt", "Co", 58.9332, "Transition Metal"},<br>
        {28, "Nickel", "Ni", 58.6934, "Transition Metal"},<br>
        {29, "Copper", "Cu", 63.546, "Transition Metal"},<br>
        {30, "Zinc", "Zn", 65.38, "Transition Metal"},<br>
        {31, "Gallium", "Ga", 69.723, "Basic Metal"},<br>
        {32, "Germanium", "Ge", 72.63, "Semi-metal"},<br>
        {33, "Arsenic", "As", 74.9216, "Semi-metal"},<br>
        {34, "Selenium", "Se", 78.971, "Non-metal"},<br>
        {35, "Bromine", "Br", 79.904, "Halogen"},<br>
        {36, "Krypton", "Kr", 83.798, "Noble Gase"},<br>
        {37, "Rubidium", "Rb", 85.4678, "Alkali Metal"},<br>
        {38, "Strontium", "Sr", 87.62, "Alkaline Earth"},<br>
        {39, "Yttrium", "Y", 88.9058, "Transition Metal"},<br>
        {40, "Zirconium", "Zr", 91.224, "Transition Metal"},<br>
        {41, "Niobium", "Nb", 92.9064, "Transition Metal"},<br>
        {42, "Molybdenum", "Mo", 95.95, "Transition Metal"},<br>
        {43, "Technetium", "Tc", 98, "Transition Metal"},<br>
        {44, "Ruthenium", "Ru", 101.07, "Transition Metal"},<br>
        {45, "Rhodium", "Rh", 102.9055, "Transition Metal"},<br>
        {46, "Palladium", "Pd", 106.42, "Transition Metal"},<br>
        {47, "Silver", "Ag", 107.8682, "Transition Metal"},<br>
        {48, "Cadmium", "Cd", 112.414, "Transition Metal"},<br>
        {49, "Indium", "In", 114.818, "Basic Metal"},<br>
        {50, "Tin", "Sn", 118.71, "Basic Metal"},<br>
        {51, "Antimony", "Sb", 121.76, "Semi-metal"},<br>
        {52, "Tellurium", "Te", 127.6, "Semi-metal"},<br>
        {53, "Iodine", "I", 126.9045, "Halogen"},<br>
        {54, "Xenon", "Xe", 131.293, "Noble Gase"},<br>
        {55, "Cesium", "Cs", 132.9055, "Alkali Metal"},<br>
        {56, "Barium", "Ba", 137.327, "Alkaline Earth"},<br>
        {57, "Lanthanum", "La", 138.9055, "Lanthanide"},<br>
        {58, "Cerium", "Ce", 140.116, "Lanthanide"},<br>
        {59, "Praseodymium", "Pr", 140.907, "Lanthanide"},<br>
        {60, "Neodymium", "Nd", 144.242, "Lanthanide"},<br>
        {61, "Promethium", "Pm", 145, "Lanthanide"},<br>
        {62, "Samarium", "Sm", 150.36, "Lanthanide"},<br>
        {63, "Europium", "Eu", 151.964, "Lanthanide"},<br>
        {64, "Gadolinium", "Gd", 157.25, "Lanthanide"},<br>
        {65, "Terbium", "Tb", 158.9253, "Lanthanide"},<br>
        {66, "Dysprosium", "Dy", 162.5, "Lanthanide"},<br>
        {67, "Holmium", "Ho", 164.9303, "Lanthanide"},<br>
        {68, "Erbium", "Er", 167.259, "Lanthanide"},<br>
        {69, "Thulium", "Tm", 168.9342, "Lanthanide"},<br>
        {70, "Ytterbium", "Yb", 173.045, "Lanthanide"},<br>
        {71, "Lutetium", "Lu", 174.9668, "Lanthanide"},<br>
        {72, "Hafnium", "Hf", 178.49, "Transition Metal"},<br>
        {73, "Tantalum", "Ta", 180.9479, "Transition Metal"},<br>
        {74, "Tungsten", "W", 183.84, "Transition Metal"},<br>
        {75, "Rhenium", "Re", 186.207, "Transition Metal"},<br>
        {76, "Osmium", "Os", 190.23, "Transition Metal"},<br>
        {77, "Iridium", "Ir", 192.217, "Transition Metal"},<br>
        {78, "Platinum", "Pt", 195.084, "Transition Metal"},<br>
        {79, "Gold", "Au", 196.9666, "Transition Metal"},<br>
        {80, "Mercury", "Hg", 200.592, "Transition Metal"},<br>
        {81, "Thallium", "Tl", 204.38, "Basic Metal"},<br>
        {82, "Lead", "Pb", 207.2, "Basic Metal"},<br>
        {83, "Bismuth", "Bi", 208.9804, "Basic Metal"},<br>
        {84, "Polonium", "Po", 209, "Semi-metal"},<br>
        {85, "Astatine", "At", 210, "Halogen"},<br>
        {86, "Radon", "Rn", 222, "Noble Gase"},<br>
        {87, "Francium", "Fr", 223, "Alkali Metal"},<br>
        {88, "Radium", "Ra", 226, "Alkaline Earth"},<br>
        {89, "Actinium", "Ac", 227, "Actinide"},<br>
        {90, "Thorium", "Th", 232.0377, "Actinide"},<br>
        {91, "Protactinium", "Pa", 231.0359, "Actinide"},<br>
        {92, "Uranium", "U", 238.0289, "Actinide"},<br>
        {93, "Neptunium", "Np", 237, "Actinide"},<br>
        {94, "Plutonium", "Pu", 244, "Actinide"},<br>
        {95, "Americium", "Am", 243, "Actinide"},<br>
        {96, "Curium", "Cm", 247, "Actinide"},<br>
        {97, "Berkelium", "Bk", 247, "Actinide"},<br>
        {98, "Californium", "Cf", 251, "Actinide"},<br>
        {99, "Einsteinium", "Es", 252, "Actinide"},<br>
        {100, "Fermium", "Fm", 257, "Actinide"},<br>
        {101, "Mendelevium", "Md", 258, "Actinide"},<br>
        {102, "Nobelium", "No", 259, "Actinide"},<br>
        {103, "Lawrencium", "Lr", 262, "Actinide"},<br>
        {104, "Rutherfordium", "Rf", 267, "Transition Metal"},<br>
        {105, "Dubnium", "Db", 270, "Transition Metal"},<br>
        {106, "Seaborgium", "Sg", 271, "Transition Metal"},<br>
        {107, "Bohrium", "Bh", 270, "Transition Metal"},<br>
        {108, "Hassium", "Hs", 277, "Transition Metal"},<br>
        {109, "Meitnerium", "Mt", 276, "Transition Metal"},<br>
        {110, "Darmstadtium", "Ds", 281, "Transition Metal"},<br>
        {111, "Roentgenium", "Rg", 280, "Transition Metal"},<br>
        {112, "Copernicium", "Cn", 285, "Transition Metal"},<br>
        {113, "Nihonium", "Nh", 284, "Basic Metal"},<br>
        {114, "Flerovium", "Fl", 289, "Basic Metal"},<br>
        {115, "Moscovium", "Mc", 288, "Basic Metal"},<br>
        {116, "Livermorium", "Lv", 293, "Basic Metal"},<br>
        {117, "Tennessine", "Ts", 294, "Halogen"},<br>
        {118, "Oganesson", "Og", 294, "Noble Gase"}<br>
    };<br>

    display(table, size);

    string query;
    while(query!="0") {
    cout << "Enter the name or symbol of the element to search: ";
    cin >> query;

    int result = search(table, size, query);
    if (result != -1) {
        cout << "Atomic Number: " << result + 1 << ":" << endl;
        cout << "Name: " << table[result].name << endl;
        cout << "Symbol: " << table[result].symbol << endl;
        cout << "Atomic Mass: " << table[result].mass << endl;
        cout << "Type: " << table[result].type << endl;
    } else {
        cout << "Element not found." << endl;
    }
    }
    return 0;
}
