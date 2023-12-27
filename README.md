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

void display(Element arr[], int size) {
    cout << "               MODERN PERIODIC TABLE" << endl;
    cout << "----------------------------------------------------------------" << endl;
    cout << "| No | Element name | Symbol | Atomic Mass | Type              |" << endl;
    cout << "----------------------------------------------------------------" << endl;
    for (int i = 0; i < size; i++) {
        cout << "|" << setw(3) << arr[i].AtomicNo << " |";
        cout << setw(13) << arr[i].name << " |";
        cout << setw(7) << arr[i].symbol << " |";
        cout << setw(12) << arr[i].mass << " |";
        cout << setw(18) << arr[i].type << " |" << endl;
    }
    cout << "----------------------------------------------------------------" << endl;
}

int search(Element arr[], int size, const string& query) {
    string Q = query;
    transform(Q.begin(), Q.end(), Q.begin(), ::toupper);

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

int main() {
    const int size = 118; 
    Element table[size] = {
        {1, "Hydrogen", "H", 1.0079, "Non-metal"},
        {2, "Helium", "He", 4.0026, "Noble Gase"},
        {3, "Lithium", "Li", 6.941, "Alkali Metal"},
        {4, "Beryllium", "Be", 9.0122, "Alkaline Earth"},
        {5, "Boron", "B", 10.811, "Semi-metal"},
        {6, "Carbon", "C", 12.0107, "Non-metal"},
        {7, "Nitrogen", "N", 14.0067, "Non-metal"},
        {8, "Oxygen", "O", 15.9994, "Non-metal"},
        {9, "Fluorine", "F", 18.9984, "Halogen"},
        {10, "Neon", "Ne", 20.1797, "Noble Gase"},
        {11, "Sodium", "Na", 22.9898, "Alkali Metal"},
        {12, "Magnesium", "Mg", 24.305, "Alkaline Earth"},
        {13, "Aluminum", "Al", 26.9815, "Basic Metal"},
        {14, "Silicon", "Si", 28.085, "Semi-metal"},
        {15, "Phosphorus", "P", 30.9738, "Non-metal"},
        {16, "Sulfur", "S", 32.06, "Non-metal"},
        {17, "Chlorine", "Cl", 35.45, "Halogen"},
        {18, "Argon", "Ar", 39.948, "Noble Gase"},
        {19, "Potassium", "K", 39.0983, "Alkali Metal"},
        {20, "Calcium", "Ca", 40.078, "Alkaline Earth"},
        {21, "Scandium", "Sc", 44.9559, "Transition Metal"},
        {22, "Titanium", "Ti", 47.867, "Transition Metal"},
        {23, "Vanadium", "V", 50.9415, "Transition Metal"},
        {24, "Chromium", "Cr", 51.9961, "Transition Metal"},
        {25, "Manganese", "Mn", 54.938, "Transition Metal"},
        {26, "Iron", "Fe", 55.845, "Transition Metal"},
        {27, "Cobalt", "Co", 58.9332, "Transition Metal"},
        {28, "Nickel", "Ni", 58.6934, "Transition Metal"},
        {29, "Copper", "Cu", 63.546, "Transition Metal"},
        {30, "Zinc", "Zn", 65.38, "Transition Metal"},
        {31, "Gallium", "Ga", 69.723, "Basic Metal"},
        {32, "Germanium", "Ge", 72.63, "Semi-metal"},
        {33, "Arsenic", "As", 74.9216, "Semi-metal"},
        {34, "Selenium", "Se", 78.971, "Non-metal"},
        {35, "Bromine", "Br", 79.904, "Halogen"},
        {36, "Krypton", "Kr", 83.798, "Noble Gase"},
        {37, "Rubidium", "Rb", 85.4678, "Alkali Metal"},
        {38, "Strontium", "Sr", 87.62, "Alkaline Earth"},
        {39, "Yttrium", "Y", 88.9058, "Transition Metal"},
        {40, "Zirconium", "Zr", 91.224, "Transition Metal"},
        {41, "Niobium", "Nb", 92.9064, "Transition Metal"},
        {42, "Molybdenum", "Mo", 95.95, "Transition Metal"},
        {43, "Technetium", "Tc", 98, "Transition Metal"},
        {44, "Ruthenium", "Ru", 101.07, "Transition Metal"},
        {45, "Rhodium", "Rh", 102.9055, "Transition Metal"},
        {46, "Palladium", "Pd", 106.42, "Transition Metal"},
        {47, "Silver", "Ag", 107.8682, "Transition Metal"},
        {48, "Cadmium", "Cd", 112.414, "Transition Metal"},
        {49, "Indium", "In", 114.818, "Basic Metal"},
        {50, "Tin", "Sn", 118.71, "Basic Metal"},
        {51, "Antimony", "Sb", 121.76, "Semi-metal"},
        {52, "Tellurium", "Te", 127.6, "Semi-metal"},
        {53, "Iodine", "I", 126.9045, "Halogen"},
        {54, "Xenon", "Xe", 131.293, "Noble Gase"},
        {55, "Cesium", "Cs", 132.9055, "Alkali Metal"},
        {56, "Barium", "Ba", 137.327, "Alkaline Earth"},
        {57, "Lanthanum", "La", 138.9055, "Lanthanide"},
        {58, "Cerium", "Ce", 140.116, "Lanthanide"},
        {59, "Praseodymium", "Pr", 140.907, "Lanthanide"},
        {60, "Neodymium", "Nd", 144.242, "Lanthanide"},
        {61, "Promethium", "Pm", 145, "Lanthanide"},
        {62, "Samarium", "Sm", 150.36, "Lanthanide"},
        {63, "Europium", "Eu", 151.964, "Lanthanide"},
        {64, "Gadolinium", "Gd", 157.25, "Lanthanide"},
        {65, "Terbium", "Tb", 158.9253, "Lanthanide"},
        {66, "Dysprosium", "Dy", 162.5, "Lanthanide"},
        {67, "Holmium", "Ho", 164.9303, "Lanthanide"},
        {68, "Erbium", "Er", 167.259, "Lanthanide"},
        {69, "Thulium", "Tm", 168.9342, "Lanthanide"},
        {70, "Ytterbium", "Yb", 173.045, "Lanthanide"},
        {71, "Lutetium", "Lu", 174.9668, "Lanthanide"},
        {72, "Hafnium", "Hf", 178.49, "Transition Metal"},
        {73, "Tantalum", "Ta", 180.9479, "Transition Metal"},
        {74, "Tungsten", "W", 183.84, "Transition Metal"},
        {75, "Rhenium", "Re", 186.207, "Transition Metal"},
        {76, "Osmium", "Os", 190.23, "Transition Metal"},
        {77, "Iridium", "Ir", 192.217, "Transition Metal"},
        {78, "Platinum", "Pt", 195.084, "Transition Metal"},
        {79, "Gold", "Au", 196.9666, "Transition Metal"},
        {80, "Mercury", "Hg", 200.592, "Transition Metal"},
        {81, "Thallium", "Tl", 204.38, "Basic Metal"},
        {82, "Lead", "Pb", 207.2, "Basic Metal"},
        {83, "Bismuth", "Bi", 208.9804, "Basic Metal"},
        {84, "Polonium", "Po", 209, "Semi-metal"},
        {85, "Astatine", "At", 210, "Halogen"},
        {86, "Radon", "Rn", 222, "Noble Gase"},
        {87, "Francium", "Fr", 223, "Alkali Metal"},
        {88, "Radium", "Ra", 226, "Alkaline Earth"},
        {89, "Actinium", "Ac", 227, "Actinide"},
        {90, "Thorium", "Th", 232.0377, "Actinide"},
        {91, "Protactinium", "Pa", 231.0359, "Actinide"},
        {92, "Uranium", "U", 238.0289, "Actinide"},
        {93, "Neptunium", "Np", 237, "Actinide"},
        {94, "Plutonium", "Pu", 244, "Actinide"},
        {95, "Americium", "Am", 243, "Actinide"},
        {96, "Curium", "Cm", 247, "Actinide"},
        {97, "Berkelium", "Bk", 247, "Actinide"},
        {98, "Californium", "Cf", 251, "Actinide"},
        {99, "Einsteinium", "Es", 252, "Actinide"},
        {100, "Fermium", "Fm", 257, "Actinide"},
        {101, "Mendelevium", "Md", 258, "Actinide"},
        {102, "Nobelium", "No", 259, "Actinide"},
        {103, "Lawrencium", "Lr", 262, "Actinide"},
        {104, "Rutherfordium", "Rf", 267, "Transition Metal"},
        {105, "Dubnium", "Db", 270, "Transition Metal"},
        {106, "Seaborgium", "Sg", 271, "Transition Metal"},
        {107, "Bohrium", "Bh", 270, "Transition Metal"},
        {108, "Hassium", "Hs", 277, "Transition Metal"},
        {109, "Meitnerium", "Mt", 276, "Transition Metal"},
        {110, "Darmstadtium", "Ds", 281, "Transition Metal"},
        {111, "Roentgenium", "Rg", 280, "Transition Metal"},
        {112, "Copernicium", "Cn", 285, "Transition Metal"},
        {113, "Nihonium", "Nh", 284, "Basic Metal"},
        {114, "Flerovium", "Fl", 289, "Basic Metal"},
        {115, "Moscovium", "Mc", 288, "Basic Metal"},
        {116, "Livermorium", "Lv", 293, "Basic Metal"},
        {117, "Tennessine", "Ts", 294, "Halogen"},
        {118, "Oganesson", "Og", 294, "Noble Gase"}
    };

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
