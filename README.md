# example1

import React, {useState} from 'react';

function Component(){
   
    const [cars, setCars] = useState([]);
    const [carYear, setCarYear] = useState(new Date(),getFullTear());
    const [carBrand, setCarBrand] = useState("");
    const [carModel, setCarModel] = useState("");

    function AddCar(){

        const newCar = {year: carYear, brand: carBrand, model: carModel};

        setCars(c => [...c, newCar]);

        setCarYear(new Date().getFullYear());
        setCarBrand("");
        setCarModel("");
    }

    function RemoveCar(index){
        setCars(c => c.filter((_, i) => i !== index));
    }

    function ChangeYear(event){
         setCarYear(event.target.value);
    }

    function ChangeBrand(event){
        setCarYear(event.target.value);
    }

    function ChangeModel(event){
        setCarYear(event.target.value);
    }

    return (<div>
             <h1>List of Car</h1>
             <ul>
                {cars.map((car, index) => 
                <li key={index} onClick={() => RemoveCar(index)}>
                    {car.brand} {car.model} {car.year}

                </li>)}
                     
             </ul>

             <input type="text" value={carsBrand} onChange={ChangeBrand} placeholder="Enter car brand"/><br/>
             <input type="text" value={carsModel} onChange={ChangeModel} placeholder="Enter car model"/><br/>
             <input type="number" value={carYear} onChange={ChangeYear}/>
             <button onClick={AddCar}>Add Car</button>
         </div>
    );
}
export default Component;
